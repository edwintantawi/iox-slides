<template>
  <div
    class="badge-base LI-profile-badge"
    data-locale="en_US"
    data-size="large"
    data-theme="light"
    data-type="HORIZONTAL"
    data-vanity="edwintantawi"
    data-version="v1"
  >
    <a
      class="badge-base__link LI-simple-link"
      href="https://id.linkedin.com/in/edwintantawi?trk=profile-badge"
      >Edwin Tantawi</a
    >
  </div>
</template>

<script>
export default {
  head() {
    return {
      script: [
        {
          src: 'https://platform.linkedin.com/badges/js/profile.js',
          type: 'text/javascript',
          defer: true,
        },
      ],
    };
  },
};
</script>
