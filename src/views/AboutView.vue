<template>
  <div class="about">
    <h1>This is an about page</h1>
    <SignupForm />
    <FindMe />
  </div>
</template>

<script>
import SignupForm from '@/components/SignupForm.vue';
import FindMe from '@/components/FindMe.vue';

export default {
  name: 'AboutView',
  components: {
    SignupForm,
    FindMe,
  },
};
</script>
