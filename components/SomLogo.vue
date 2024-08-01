<!-- SomLogo.vue -->
<template>
  <div>
    <NuxtLink class="btn btn-ghost text-xl" to="/">
    <span>S ☻ M</span>
  </NuxtLink>
  <NuxtLink to="/blog/happyhsryu">
    <span>go to blog</span>
  </NuxtLink>
  </div>
  
</template>

<style>
.btn {
    display: inline-flex;
    height: 3rem;
    min-height: 3rem;
    flex-shrink: 0;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    user-select: none;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    border-radius: var(--rounded-btn, .5rem);
    border-color: transparent;
    border-color: oklch(var(--btn-color, var(--b2)) / var(--tw-border-opacity));
    padding-left: 1rem;
    padding-right: 1rem;
    text-align: center;
    font-size: .875rem;
    line-height: 1em;
    gap: .5rem;
    font-weight: 600;
    text-decoration-line: none;
    transition-duration: .2s;
    transition-timing-function: cubic-bezier(0,0,.2,1);
    border-width: var(--border-btn, 1px);
    animation: button-pop var(--animation-btn, .25s) ease-out;
    transition-property: color, background-color, border-color, opacity, box-shadow, transform;
    --tw-text-opacity: 1;
    color: var(--fallback-bc, oklch(var(--bc) / var(--tw-text-opacity)));
    --tw-shadow: 0 1px 2px 0 rgb(0 0 0 / .05);
    --tw-shadow-colored: 0 1px 2px 0 var(--tw-shadow-color);
    box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
    outline-color: var(--fallback-bc, oklch(var(--bc) / 1));
    background-color: oklch(var(--btn-color, var(--b2)) / var(--tw-bg-opacity));
    --tw-bg-opacity: 1;
    --tw-border-opacity: 1;
}
.btn-ghost {
    border-width: 1px;
    border-color: transparent;
    background-color: transparent;
    color: currentColor;
    --tw-shadow: 0 0 #0000;
    --tw-shadow-colored: 0 0 #0000;
    box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
    outline-color: currentColor;
}
.text-xl {
    font-size: 1.25rem;
    line-height: 1.75rem;
}
</style>

