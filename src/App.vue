<template>
  <div
    id="app"
    class="min-h-screen bg-gray-200 antialiased xl:flex xl:flex-col xl:h-screen"
  >
    <site-header class="xl:flex-shrink-0" />
    <div class="xl:flex-1 xl:flex xl:overflow-y-hidden">
      <search-filters />
      <main class="py-6 xl:flex-1 xl:overflow-x-hidden">
        <div
          v-for="(location, i) in locations"
          :key="i"
          :class="{ 'mt-6': i > 0 }"
        >
          <div class="px-4 xl:px-8">
            <h3 class="text-gray-900 text-xl">{{ location.title }}</h3>
            <p class="text-gray-600">{{ location.description }}</p>
          </div>
          <div class="mt-6 sm:overflow-x-auto sm:overflow-y-hidden">
            <div class="px-4 sm:inline-flex sm:pt-2 sm:pb-8 xl:px-8">
              <div
                v-for="(property, i) in location.properties"
                :key="i"
                :class="{ 'mt-10 sm:ml-4': i > 0 }"
                class="sm:mt-0 sm:w-80 sm:flex-shrink-0"
              >
                <property-card :property="property" />
              </div>
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>
<script>
import SiteHeader from "@/components/SiteHeader";
import SearchFilters from "@/components/SearchFilters";
import PropertyCard from "@/components/PropertyCard";
import SiteHeader from "./components/SiteHeader.vue";
import SearchFilters from "./components/SearchFilters.vue";
import PropertyCard from "./components/PropertyCard.vue";

export default {
  name: "app",
  components: {
    PropertyCard,
    SiteHeader,
    SearchFilters,
  },
  data() {
    return {
      locations: [
        {
          title: "Los Angeles",
          description:
            "Live like the stars in these luxurious Southern California estates.",
          properties: [
            {
              imageUrl:
                "https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
              beds: 3,
              baths: 2,
              title: "Modern home in city center",
              price: 190000,
              reviewCount: 34,
              rating: 4,
            },
            {
              imageUrl:
                "https://images.unsplash.com/photo-1513584684374-8bab748fbf90?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
              beds: 4,
              baths: 1,
              title: "Quiet living outside the city",
              price: 175000,
              reviewCount: 12,
              rating: 3,
            },
            {
              imageUrl:
                "https://images.unsplash.com/photo-1502005229762-cf1b2da7c5d6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80",
              beds: 5,
              baths: 4,
              title: "Renovated apartment uptown",
              price: 200000,
              reviewCount: 54,
              rating: 5,
            },
            {
              imageUrl:
                "https://images.unsplash.com/photo-1505691938895-1758d7feb511?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
              beds: 3,
              baths: 2,
              title: "Family home in the suburbs",
              price: 115000,
              reviewCount: 34,
              rating: 4,
            },
          ],
        },
        {
          title: "Phoenix",
          description:
            "Escape the cold and enjoy great weather without breaking the bank.",
          properties: [
            {
              imageUrl:
                "https://images.unsplash.com/photo-1447958272669-9c562446304f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80",
              beds: 3,
              baths: 2,
              title: "Modern home in city center",
              price: 190000,
              reviewCount: 34,
              rating: 4,
            },
            {
              imageUrl:
                "https://images.unsplash.com/photo-1475855581690-80accde3ae2b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=80",
              beds: 4,
              baths: 1,
              title: "Quiet living outside the city",
              price: 175000,
              reviewCount: 12,
              rating: 3,
            },
            {
              imageUrl:
                "https://images.unsplash.com/photo-1472224371017-08207f84aaae?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
              beds: 5,
              baths: 4,
              title: "Renovated apartment uptown",
              price: 200000,
              reviewCount: 54,
              rating: 5,
            },
            {
              imageUrl:
                "https://images.unsplash.com/photo-1484154218962-a197022b5858?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
              beds: 3,
              baths: 2,
              title: "Family home in the suburbs",
              price: 115000,
              reviewCount: 34,
              rating: 4,
            },
          ],
        },
      ],
    };
  },
};
</script>
<style>
</style>