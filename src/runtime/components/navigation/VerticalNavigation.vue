<template>
  <nav :class="wrapperClass">
    <Link
      v-for="(link, index) of links"
      v-slot="{ isActive }"
      :key="index"
      v-bind="link"
      :class="[baseClass, spacingClass]"
      :active-class="activeClass"
      :inactive-class="inactiveClass"
      @click="link.click && link.click()"
      @keyup.enter="$event.target.blur()"
    >
      <slot name="avatar" :link="link">
        <Avatar
          v-if="link.avatar"
          v-bind="{ size: 'xs', ...link.avatar }"
          :class="[avatarBaseClass, link.label && avatarSpacingClass]"
        />
      </slot>
      <slot name="icon" :link="link">
        <Icon
          v-if="link.icon"
          :name="link.icon"
          :class="[iconBaseClass, link.label && iconSpacingClass, isActive ? iconActiveClass : iconInactiveClass, link.iconClass]"
        />
      </slot>
      <slot :link="link">
        <span v-if="link.label" class="truncate">{{ link.label }}</span>
      </slot>
      <slot name="badge" :link="link">
        <span v-if="link.badge" :class="[badgeBaseClass, isActive ? badgeActiveClass : badgeInactiveClass]">
          {{ link.badge }}
        </span>
      </slot>
    </Link>
  </nav>
</template>

<script setup lang="ts">
import type { PropType } from 'vue'
import Icon from '../elements/Icon.vue'
import Link from '../elements/Link.vue'
import Avatar from '../elements/Avatar.vue'
import type { Avatar as AvatarType } from '../../types/avatar'
import $ui from '#build/ui'

defineProps({
  links: {
    type: Array as PropType<{
      label: string
      icon?: string
      iconClass?: string
      avatar?: Partial<AvatarType>
      click?: Function
      badge?: string
    }[]>,
    required: true
  },
  wrapperClass: {
    type: String,
    default: () => $ui.verticalNavigation.wrapper
  },
  baseClass: {
    type: String,
    default: () => $ui.verticalNavigation.base
  },
  spacingClass: {
    type: String,
    default: () => $ui.verticalNavigation.spacing
  },
  activeClass: {
    type: String,
    default: () => $ui.verticalNavigation.active
  },
  inactiveClass: {
    type: String,
    default: () => $ui.verticalNavigation.inactive
  },
  iconBaseClass: {
    type: String,
    default: () => $ui.verticalNavigation.icon.base
  },
  iconSpacingClass: {
    type: String,
    default: () => $ui.verticalNavigation.icon.spacing
  },
  iconActiveClass: {
    type: String,
    default: () => $ui.verticalNavigation.icon.active
  },
  iconInactiveClass: {
    type: String,
    default: () => $ui.verticalNavigation.icon.inactive
  },
  avatarBaseClass: {
    type: String,
    default: () => $ui.verticalNavigation.avatar.base
  },
  avatarSpacingClass: {
    type: String,
    default: () => $ui.verticalNavigation.avatar.spacing
  },
  badgeBaseClass: {
    type: String,
    default: () => $ui.verticalNavigation.badge.base
  },
  badgeActiveClass: {
    type: String,
    default: () => $ui.verticalNavigation.badge.active
  },
  badgeInactiveClass: {
    type: String,
    default: () => $ui.verticalNavigation.badge.inactive
  }
})
</script>

<script lang="ts">
export default { name: 'UVerticalNavigation' }
</script>