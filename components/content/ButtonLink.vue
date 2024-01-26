<script setup>
defineProps({
  href: {
    type: String,
    required: true,
  },
  external: {
    type: Boolean,
    default: false,
  },
  icon: {
    type: String,
    default: '',
  },
})
</script>

<template>
  <span class="not-prose">
    <a :href="href" :class="['custom-link', external ? 'external' : '']">
      <Icon v-if="icon" :name="icon" class="custom-icon" />
      <ContentSlot :use="$slots.default" unwrap="p" />
    </a>
  </span>
</template>

<style>
.custom-link {
  display: inline-flex;
  align-items: center;
  gap: 1rem;
  color: white;
  background-color: #0047e1 ; /* Remplacez par la couleur de fond souhaitée */
  padding: 0.25rem 0.5rem;
  border-radius: 0.25rem;
  text-decoration: none;
}

.custom-link.external {
  background-color: #0047e1; /* Couleur de fond différente pour les liens externes */
}

.custom-icon {
  width: 1rem; /* Ajustez la taille de l'icône selon vos besoins */
  height: 1rem;
  /* Ajoutez d'autres styles d'icône si nécessaire */
}
</style>
