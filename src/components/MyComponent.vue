<template>
  <!-- <MyComponent> template -->
  <div>
    <slot :myName="fullName" :job="job"></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fullName: 'Nguyen Truong Giang',
      job: 'deverloper',
    };
  },
};
</script>

<script></script>
