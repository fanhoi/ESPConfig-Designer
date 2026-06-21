<template>
  <div
    v-if="activeComponentBusLabels || activeComponentProtocolLabels || activeComponentSystemLabels || activeComponentNetworkLabels || activeComponentComponentLabels"
    class="notice notice--warning component-bus-note"
  >
    <template v-if="activeComponentBusLabels">
      Убедитесь, что {{ activeComponentBusLabels }} настроен(ы) правильно.
      <a href="#" class="preview-callout-link" @click.prevent="emit('focus-bus')">
        ШИНЫ
      </a>
    </template>
    <template v-if="activeComponentProtocolLabels">
      <br v-if="activeComponentBusLabels" />
      Убедитесь, что {{ activeComponentProtocolLabels }} настроен(ы) правильно.
      <a href="#" class="preview-callout-link" @click.prevent="emit('focus-protocol')">
        ПРОТОКОЛЫ
      </a>
    </template>
    <template v-if="activeComponentSystemLabels">
      <br v-if="activeComponentBusLabels || activeComponentProtocolLabels" />
      Убедитесь, что {{ activeComponentSystemLabels }} настроен(ы) правильно.
      <a href="#" class="preview-callout-link" @click.prevent="emit('focus-system')">
        СИСТЕМА
      </a>
    </template>
    <template v-if="activeComponentNetworkLabels">
      <br v-if="activeComponentBusLabels || activeComponentProtocolLabels || activeComponentSystemLabels" />
      Убедитесь, что {{ activeComponentNetworkLabels }} настроен(ы) правильно.
      <a href="#" class="preview-callout-link" @click.prevent="emit('focus-network')">
        СЕТЬ
      </a>
    </template>
    <template v-if="activeComponentComponentLabels">
      <br
        v-if="activeComponentBusLabels || activeComponentProtocolLabels || activeComponentSystemLabels || activeComponentNetworkLabels"
      />
      Убедитесь, что компоненты {{ activeComponentComponentLabels }} настроены правильно.
    </template>
  </div>
</template>

<script setup>
defineProps({
  activeComponentBusLabels: { type: String, default: "" },
  activeComponentProtocolLabels: { type: String, default: "" },
  activeComponentSystemLabels: { type: String, default: "" },
  activeComponentNetworkLabels: { type: String, default: "" },
  activeComponentComponentLabels: { type: String, default: "" }
});

const emit = defineEmits(["focus-bus", "focus-protocol", "focus-system", "focus-network"]);
</script>
