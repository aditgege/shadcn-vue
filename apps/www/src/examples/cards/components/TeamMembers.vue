<script setup lang="ts">
import ChevronDownIcon from '~icons/radix-icons/chevron-down'

import {
  Avatar,
  AvatarFallback,
  AvatarImage,
} from '@/lib/registry/default/ui/avatar'
import { Button } from '@/lib/registry/default/ui/button'
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from '@/lib/registry/default/ui/card'

import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from '@/lib/registry/default/ui/popover'
</script>

<template>
  <Card>
    <CardHeader>
      <CardTitle>Team Members</CardTitle>
      <CardDescription>
        Invite your team members to collaborate.
      </CardDescription>
    </CardHeader>
    <CardContent class="grid gap-6">
      <div class="flex items-center justify-between space-x-4">
        <div class="flex items-center space-x-4">
          <Avatar>
            <AvatarImage src="/avatars/01.png" />
            <AvatarFallback>OM</AvatarFallback>
          </Avatar>
          <div>
            <p class="text-sm font-medium leading-none">
              Sofia Davis
            </p>
            <p class="text-sm text-muted-foreground">
              m@example.com
            </p>
          </div>
        </div>
        <Popover>
          <PopoverTrigger as-child>
            <Button variant="outline" class="ml-auto">
              Owner
              <ChevronDownIcon class="ml-2 h-4 w-4 text-muted-foreground" />
            </Button>
          </PopoverTrigger>
          <PopoverContent class="p-0" align="end">
            <!-- <Command>
                <CommandInput placeholder="Select new role..." />
                <CommandList>
                  <CommandEmpty>No roles found.</CommandEmpty>
                  <CommandGroup>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Viewer</p>
                      <p class="text-sm text-muted-foreground">
                        Can view and comment.
                      </p>
                    </CommandItem>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Developer</p>
                      <p class="text-sm text-muted-foreground">
                        Can view, comment and edit.
                      </p>
                    </CommandItem>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Billing</p>
                      <p class="text-sm text-muted-foreground">
                        Can view, comment and manage billing.
                      </p>
                    </CommandItem>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Owner</p>
                      <p class="text-sm text-muted-foreground">
                        Admin-level access to all resources.
                      </p>
                    </CommandItem>
                  </CommandGroup>
                </CommandList>
              </Command> -->
          </PopoverContent>
        </Popover>
      </div>
      <div class="flex items-center justify-between space-x-4">
        <div class="flex items-center space-x-4">
          <Avatar>
            <AvatarImage src="/avatars/02.png" />
            <AvatarFallback>JL</AvatarFallback>
          </Avatar>
          <div>
            <p class="text-sm font-medium leading-none">
              Jackson Lee
            </p>
            <p class="text-sm text-muted-foreground">
              p@example.com
            </p>
          </div>
        </div>
        <Popover>
          <PopoverTrigger as-child>
            <Button variant="outline" class="ml-auto">
              Member
              <ChevronDownIcon class="ml-2 h-4 w-4 text-muted-foreground" />
            </Button>
          </PopoverTrigger>
          <PopoverContent class="p-0" align="end">
            <!-- <Command>
                <CommandInput placeholder="Select new role..." />
                <CommandList>
                  <CommandEmpty>No roles found.</CommandEmpty>
                  <CommandGroup class="p-1.5">
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Viewer</p>
                      <p class="text-sm text-muted-foreground">
                        Can view and comment.
                      </p>
                    </CommandItem>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Developer</p>
                      <p class="text-sm text-muted-foreground">
                        Can view, comment and edit.
                      </p>
                    </CommandItem>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Billing</p>
                      <p class="text-sm text-muted-foreground">
                        Can view, comment and manage billing.
                      </p>
                    </CommandItem>
                    <CommandItem class="teamaspace-y-1 flex flex-col items-start px-4 py-2">
                      <p>Owner</p>
                      <p class="text-sm text-muted-foreground">
                        Admin-level access to all resources.
                      </p>
                    </CommandItem>
                  </CommandGroup>
                </CommandList>
              </Command> -->
          </PopoverContent>
        </Popover>
      </div>
    </CardContent>
  </Card>
</template>
