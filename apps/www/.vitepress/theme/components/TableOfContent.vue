<script setup lang="ts">
import { onContentUpdated } from 'vitepress'
import { shallowRef } from 'vue'
import type { TableOfContents, TableOfContentsItem } from '../types/docs'
import TableOfContentTree from './TableOfContentTree.vue'
import { Collapsible, CollapsibleContent, CollapsibleTrigger } from '@/lib/registry/default/ui/collapsible'
import { buttonVariants } from '@/lib/registry/default/ui/button'

const headers = shallowRef<TableOfContents>()

function getHeadingsWithHierarchy(divId: string) {
  const div = document.querySelector(divId)
  if (!div)
    return { items: [] }

  const headings: HTMLHeadingElement[] = Array.from(
    div.querySelectorAll('h2, h3'),
  )
  const hierarchy: TableOfContents = { items: [] }
  let currentLevel: TableOfContentsItem | undefined

  headings.forEach((heading: HTMLHeadingElement) => {
    const level = Number.parseInt(heading.tagName.charAt(1))
    if (!heading.id) {
      const newId = heading.innerText
        .replaceAll(/[^a-zA-Z0-9 ]/g, '')
        .replaceAll(' ', '-')
        .toLowerCase()
      heading.id = `${newId}`
    }

    const item: TableOfContentsItem = {
      title: heading.textContent || '',
      url: `#${heading.id}`,
      items: [],
    }

    if (level === 2) {
      hierarchy.items.push(item)
      currentLevel = item
    }
    else if (level === 3 && currentLevel?.items) {
      currentLevel.items.push(item)
    }
  })
  return hierarchy
}

onContentUpdated(() => {
  headers.value = getHeadingsWithHierarchy('.vp-doc')
})
</script>

<template>
  <div class="space-y-2 hidden xl:block">
    <p class="font-medium">
      On This Page
    </p>
    <TableOfContentTree :tree="headers" :level="1" />
  </div>

  <div class="block xl:hidden mb-6">
    <Collapsible>
      <CollapsibleTrigger :class="buttonVariants({ variant: 'outline' })">
        On This Page
      </CollapsibleTrigger>
      <CollapsibleContent class="text-sm mt-4 border-l pl-4">
        <TableOfContentTree :tree="headers" :level="1" />
      </CollapsibleContent>
    </Collapsible>
  </div>
</template>
