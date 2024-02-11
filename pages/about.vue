<template>
  <section class="about-page">
    <div class="container">
      <h1 class="page-title">About Our Merch</h1>

      <div class="section section-about">
        <h2 class="section-title">Our Story</h2>
        <p>{{ aboutText }}</p>
        <p>{{ aboutText }}</p>
      </div>

      <div class="section section-team">
        <h2 class="section-title">The Creative Minds Behind Our Merch</h2>
        <p>{{ aboutText }}</p>
        <p>{{ aboutText }}</p>

        <ul class="team-list">
          <p v-for="member in teamMembers" :key="member.id">
            <img
              :src="member.image"
              :alt="member.name"
              class="team-member-image"
            />
            <div class="team-member-info">
              <h3>{{ member.name }}</h3>
              <p>{{ member.role }}</p>
            </div>
          </p>
        </ul>
      </div>

      <div class="section section-contact">
        <h2 class="section-title">Get in Touch About Our Merch</h2>
        <p>{{ aboutText }}</p>
        <p>Questions about our designs or sizing? We're happy to help!</p>
        <ul class="contact-list">
          <p>
            <a href="mailto:{{ email }}">Email: {{ email }}</a>
          </p>
          <p>
            <a :href="`tel:{{phoneNumber}}`">Phone: {{ phoneNumber }}</a>
          </p>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const aboutText = ref(
  "Our merch is more than just clothes and accessories. It's a statement of who you are and what you stand for. We design each piece with passion and creativity, using high-quality materials and attention to detail. Whether you're looking for a bold statement piece or something more subtle to add to your everyday style, we have something for everyone. Express yourself and make a statement with our unique merch!"
);
const teamMembers = ref([
  {
    id: 1,
    name: "John Doe",
    role: "CEO",
    image: "https://franchisematch.com/wp-content/uploads/2015/02/john-doe.jpg",
  },
  {
    id: 2,
    name: "Jane Smith",
    role: "Designer",
    image:
      "https://www.losingcontrol.org/wp-content/uploads/2017/05/speaker-1.jpg",
  },
  {
    id: 3,
    name: "Navein",
    role: "Developer",
    image: "https://media.licdn.com/dms/image/D5603AQG57z4z9M5q-Q/profile-displayphoto-shrink_800_800/0/1697019767005?e=1713398400&v=beta&t=bOCX6WoOPL-K01x9pZB0v3QpVer69yOoPPrppjqGtq8",
  },
  // ... more team members
]);
const email = ref("naveinthiran97@gmail.com");
const phoneNumber = ref("011-2061-6323");
</script>

<style scoped>
h1 {
  margin-bottom: 20px;
  font-size: 36px;
  font-weight: 700; /* Add bolder font weight for impact */
  text-transform: uppercase; /* Capitalize for a polished look */
}

h2 {
  margin-bottom: 15px;
  font-size: 28px;
  font-weight: 500; /* Slightly bolder weight for subheadings */
}

p {
  margin: 20px 0;
  font-size: 16px; /* Ensure comfortable readability */
  line-height: 1.5; /* Enhance readability with adequate spacing */
}

.team-member-image {
  width: 300px;
  height: 300px;
  object-fit: cover;
  margin-left: 40px;
  margin-right: 40px;
  border-radius: 50%; /* Create a circular shape */
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.15); /* Add a subtle, soft shadow */
}

.team-member-info {
  text-align: center; /* Center text within the info box */
}

.team-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start; /* Evenly distribute images */
  margin: 40px 0; /* Add spacing between sections */
}

.section {
  margin-bottom: 40px; /* Add spacing between sections */
}
</style>
