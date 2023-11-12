<template>
  <div class="row">
    <div class="col-md-8">
      <edit-profile-form :model="model"> </edit-profile-form>
    </div>
    <div class="col-md-4">
      <user-card :user="user"></user-card>
    </div>
  </div>
</template>
<script>
import EditProfileForm from "./Profile/EditProfileForm";
import UserCard from "./Profile/UserCard";
export default {
  components: {
    EditProfileForm,
    UserCard,
  },
  data() {
    return {
      model: {
        company: "FORSIT",
        email: "hamzashiqbal@email.com",
        username: "Hamza123",
        firstName: "Hamza",
        lastName: "Ehsan",
        address: "abc, South Korea",
        city: "-",
        country: "South Korea",
        about: "Vue.js | React.js | React Native | Next.js",
      },
      user: {
        fullName: "Hamza Ehsan",
        title: "CEO",
        description: ``,
      },
    };
  },
};
</script>
<style></style>
