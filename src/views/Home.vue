<template>
  <div>
    <section id="start" class="max-width">
      <!-- landing -->
      <Landing />

      <!-- feature cards -->
      <div class="cards">
        <FeatureCard
          v-for="(featureCard, index) in featureCards"
          :key="index"
          :content="featureCard"
        />
      </div>

      <!-- about -->
      <AboutSection />

      <!-- contact -->
      <ContactSection />
    </section>
    <!-- footer -->
    <Footer />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Landing from "@/components/home/Landing.component.vue";
import FeatureCard from "@/components/home/FeatureCard.component.vue";
import { FeatureCardContent } from "@/components/home/FeatureCard.component.vue";
import AboutSection from "@/components/home/AboutSection.component.vue";
import ContactSection from "@/components/home/ContactSection.component.vue";
import Footer from "@/components/home/Footer.component.vue";

@Component({
  components: { Landing, FeatureCard, AboutSection, ContactSection, Footer },
})
export default class Home extends Vue {
  featureCards = [
    {
      title: "Transaction Tracking",
      text:
        "Track and categorize all your incomes and expenses. Track your spending history. Improve your financial " +
        "health and learn to save money and budget.",
      icon: "mdi-cash-multiple",
    },
    {
      title: "Multiple Accounts",
      text:
        "Create multiple accounts for different purposes like Current account, Saving accounts, Investments, and " +
        "Cash...",
      icon: "mdi-bank-outline",
    },
    {
      title: "Analyze data",
      text:
        "Analyze financial reports of your income, expenses, and cashflow. Visualize the balance evolution of spending " +
        "by category and more...",
      icon: "mdi-finance",
    },
  ] as FeatureCardContent[];
}
</script>

<style scoped>
.cards {
  display: flex;
  gap: 2.5rem;
  width: 100%;
  justify-content: center;
  flex-wrap: wrap;
  margin-top: 3rem;
}

#start {
  margin-bottom: 8rem;
}

@media only screen and (max-width: 1250px) {
  .cards {
    margin-top: 8rem;
  }
}

@media only screen and (max-width: 400px) {
  .cards {
    margin-top: 4rem;
  }
}
</style>
