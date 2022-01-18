<template>
  <nav>
      <ul class="flex gap-2">
        <li 
            v-for="route in routes"
            :key="route.label"
        >
            <a
                class="text-blue-600 visited:text-purple-600"
                :href="route.href"
                v-text="route.label"
            />
        </li>
      </ul>
  </nav>
</template>

<script>
export default {
    data: () => ({
        routes: [
            {
                label: 'Home',
                href: 'https://github.com/calamarte'
            },
            {
                label: 'Información',
                href: 'https://github.com/calamarte'
            },
            {
                label: 'Login',
                href: 'https://github.com/calamarte'
            }
        ]
    })
}
</script>
