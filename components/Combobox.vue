<script setup lang="ts">
import { ref } from 'vue'
import { ComboboxAnchor, ComboboxContent, ComboboxEmpty, ComboboxGroup, ComboboxInput, ComboboxItem, ComboboxItemIndicator, ComboboxLabel, ComboboxRoot, ComboboxSeparator, ComboboxTrigger, ComboboxViewport } from 'radix-vue'
import { Icon } from '@iconify/vue'
import './styles.css'

const v = ref('')
const options = ['山手線']
</script>

<template>
  <ComboboxRoot
    v-model="v"
    class="ComboboxRoot"
  >
    <ComboboxAnchor class="ComboboxAnchor">
      <ComboboxInput
        class="ComboboxInput"
        placeholder="Placeholder..."
      />
      <ComboboxTrigger>
        <Icon
          icon="radix-icons:chevron-down"
          class="ComboboxIcon"
        />
      </ComboboxTrigger>
    </ComboboxAnchor>

    <ComboboxContent class="ComboboxContent">
      <ComboboxViewport class="ComboboxViewport">
        <ComboboxEmpty class="ComboboxEmpty" />

        <ComboboxGroup>
          <ComboboxLabel class="ComboboxLabel">
            Train Lines
          </ComboboxLabel>

          <ComboboxItem
            v-for="(option, index) in options"
            :key="index"
            class="ComboboxItem"
            :value="option"
          >
            <ComboboxItemIndicator
              class="ComboboxItemIndicator"
            >
              <Icon icon="radix-icons:check" />
            </ComboboxItemIndicator>
            <span>
              {{ option }}
            </span>
          </ComboboxItem>
          <ComboboxSeparator class="ComboboxSeparator" />
        </ComboboxGroup>
      </ComboboxViewport>
    </ComboboxContent>
  </ComboboxRoot>
</template>