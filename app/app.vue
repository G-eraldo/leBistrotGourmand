<!-- eslint-disable vue/first-attribute-linebreak -->
<template>
  <div class="font-body text-slate-800 bg-slate-50">

    <nav class="fixed w-full z-50 transition-all duration-300"
      :class="isScrolled ? 'bg-white shadow-md py-2' : 'bg-transparent py-6 text-white'">
      <div class="container mx-auto px-6 flex justify-between items-center">
        <a href="#" class="text-2xl font-serif font-bold tracking-wider uppercase">
          Le Bistro Gourmand
        </a>

        <div class="hidden md:flex space-x-8 font-medium text-sm tracking-wide">
          <a v-for="link in links" :key="link.text" :href="link.href" class="hover:text-amber-500 transition-colors">
            {{ link.text }}
          </a>
        </div>

        <button class="md:hidden text-2xl" @click="mobileMenuOpen = !mobileMenuOpen">
          ☰
        </button>
      </div>

      <div v-if="mobileMenuOpen"
        class="absolute top-full left-0 w-full bg-white text-slate-900 shadow-lg flex flex-col items-center py-4 space-y-4 md:hidden">
        <a v-for="link in links" :key="link.text" :href="link.href" @click="mobileMenuOpen = false">
          {{ link.text }}
        </a>
      </div>
    </nav>

    <section id="accueil" class="relative h-screen flex items-center justify-center text-center text-white">
      <div class="absolute inset-0 bg-black/50 z-10" />
      <img src="https://res.cloudinary.com/dlnbsf2ed/image/upload/v1766328695/istockphoto-1428412216-612x612_fo1r7u.jpg"
        class="absolute inset-0 w-full h-full object-cover" alt="Restaurant Interior">

      <div class="relative z-20 px-4">
        <span class="block text-amber-400 text-lg md:text-xl tracking-[0.2em] mb-4 uppercase">Bienvenue à table</span>
        <h1 class="text-5xl md:text-7xl font-serif font-bold mb-8 leading-tight">
          Plaisir & <br> <i class="text-amber-400">Gourmandise</i>
        </h1>
        <a href="#menu"
          class="inline-block border-2 border-amber-400 text-amber-400 px-8 py-3 hover:bg-amber-400 hover:text-black transition-all duration-300 uppercase tracking-widest text-sm font-bold">
          Voir le Menu
        </a>
      </div>
    </section>

    <section id="apropos" class="py-20 md:py-32 container mx-auto px-6">
      <div class="flex flex-col md:flex-row items-center gap-12">
        <div class="md:w-1/2">
          <img
            src="https://images.unsplash.com/photo-1559339352-11d035aa65de?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80"
            class="rounded shadow-xl shadow-amber-900/10 w-full" alt="Chef cooking">
        </div>
        <div class="md:w-1/2 space-y-6">
          <h2 class="text-4xl font-serif font-bold text-slate-900">Notre Histoire</h2>
          <div class="w-16 h-1 bg-amber-500" />
          <p class="text-slate-600 leading-relaxed">
            Le <strong>Bistro Gourmand</strong> est né d'une envie simple : proposer une cuisine généreuse et raffinée.
            Nous sélectionnons nos produits directement auprès des producteurs locaux pour garantir une fraîcheur
            absolue.
          </p>
          <p class="text-slate-600 leading-relaxed">
            Ici, pas de chichis, juste le goût du vrai. Venez partager un moment convivial dans notre établissement où
            chaque client est reçu comme un ami.
          </p>
        </div>
      </div>
    </section>

    <section id="menu" class="py-20 bg-slate-900 text-white">
      <div class="container mx-auto px-6">
        <div class="text-center mb-16">
          <span class="text-amber-500 uppercase tracking-widest text-sm font-bold">Cuisine de marché</span>
          <h2 class="text-4xl font-serif mt-2">La Carte du Bistro</h2>
        </div>

        <div class="grid md:grid-cols-2 gap-12 max-w-4xl mx-auto">
          <div>
            <h3 class="text-2xl font-serif text-amber-400 mb-6 border-b border-slate-700 pb-2">Entrées</h3>
            <div v-for="item in menu.starters" :key="item.name" class="mb-6 group">
              <div class="flex justify-between items-baseline">
                <h4 class="text-xl font-medium group-hover:text-amber-200 transition-colors">{{ item.name }}</h4>
                <span class="text-amber-500 font-bold">{{ item.price }}€</span>
              </div>
              <p class="text-slate-400 text-sm mt-1 italic">{{ item.desc }}</p>
            </div>
          </div>

          <div>
            <h3 class="text-2xl font-serif text-amber-400 mb-6 border-b border-slate-700 pb-2">Plats</h3>
            <div v-for="item in menu.mains" :key="item.name" class="mb-6 group">
              <div class="flex justify-between items-baseline">
                <h4 class="text-xl font-medium group-hover:text-amber-200 transition-colors">{{ item.name }}</h4>
                <span class="text-amber-500 font-bold">{{ item.price }}€</span>
              </div>
              <p class="text-slate-400 text-sm mt-1 italic">{{ item.desc }}</p>
            </div>
          </div>
        </div>

        <div class="text-center mt-12">
          <p class="text-slate-400 text-sm">* Nos plats sont faits maison.</p>
        </div>
      </div>
    </section>

    <section id="contact" class="py-20 container mx-auto px-6">
      <div class="max-w-4xl mx-auto bg-white rounded-lg shadow-2xl overflow-hidden flex flex-col md:flex-row">

        <div class="bg-amber-500 p-10 md:w-2/5 text-white flex flex-col justify-between">
          <div>
            <h3 class="text-2xl font-serif font-bold mb-6">Informations</h3>
            <div class="space-y-4">
              <p>📍 12 Rue de la Gastronomie,<br>75001 Paris</p>
              <p>📞 01 23 45 67 89</p>
              <p>✉️ reservation@bistrogourmand.fr</p>
            </div>
          </div>
          <div class="mt-10">
            <h4 class="font-bold mb-2">Horaires</h4>
            <p class="text-sm opacity-90">Mar - Dim : 19h00 - 23h00</p>
            <p class="text-sm opacity-90">Ven - Dim : 12h00 - 14h30</p>
          </div>
        </div>

        <div class="p-10 md:w-3/5">
          <h3 class="text-2xl font-serif font-bold text-slate-800 mb-6">Réserver une table</h3>
          <form class="space-y-4" @submit.prevent="submitForm">
            <div class="grid grid-cols-2 gap-4">
              <input type="text" placeholder="Nom"
                class="w-full border p-3 rounded focus:outline-none focus:border-amber-500 bg-slate-50">
              <input type="text" placeholder="Tel"
                class="w-full border p-3 rounded focus:outline-none focus:border-amber-500 bg-slate-50">
            </div>
            <input type="email" placeholder="Email"
              class="w-full border p-3 rounded focus:outline-none focus:border-amber-500 bg-slate-50">
            <div class="grid grid-cols-2 gap-4">
              <input type="date"
                class="w-full border p-3 rounded focus:outline-none focus:border-amber-500 bg-slate-50">
              <select class="w-full border p-3 rounded focus:outline-none focus:border-amber-500 bg-slate-50">
                <option>2 Personnes</option>
                <option>4 Personnes</option>
                <option>6+ Personnes</option>
              </select>
            </div>
            <textarea placeholder="Message spécial (allergies, anniversaire...)" rows="3"
              class="w-full border p-3 rounded focus:outline-none focus:border-amber-500 bg-slate-50" />
            <button class="w-full bg-slate-900 text-white py-3 font-bold hover:bg-slate-800 transition-colors">
              Confirmer la demande
            </button>
          </form>
        </div>
      </div>
    </section>

    <footer class="bg-slate-900 text-slate-500 py-8 text-center text-sm border-t border-slate-800">
      <p>&copy; 2025 Le Bistro Gourmand. Site fiction pour Portfolio.</p>
    </footer>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue';

// Données du menu
const menu = {
  starters: [
    { name: "Œuf Parfait Bio", price: 12, desc: "Crème de champignons et noisettes torréfiées" },
    { name: "Terrine de Campagne", price: 14, desc: "Pickles maison et pain de campagne grillé" },
    { name: "Gravlax de Saumon", price: 16, desc: "Crème d'aneth et blinis tièdes" },
  ],
  mains: [
    { name: "Magret de Canard", price: 26, desc: "Miel et épices, purée de patates douces" },
    { name: "Tartare de Bœuf au Couteau", price: 22, desc: "Préparé minute, frites maison" },
    { name: "Pavé de Lieu Jaune", price: 24, desc: "Légumes de saison glacés et beurre blanc" },
  ]
};

const links = [
  { text: 'Accueil', href: '#accueil' },
  { text: 'À Propos', href: '#apropos' },
  { text: 'Menu', href: '#menu' },
  { text: 'Réserver', href: '#contact' },
];

// État pour le menu mobile et le scroll
const mobileMenuOpen = ref(false);
const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

// Gestionnaires d'événements du cycle de vie
onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

const submitForm = () => {
  alert("Demande envoyée au Bistro Gourmand ! (Simulation)");
};
</script>

<style>
/* Ajout du smooth scroll pour toute la page */
html {
  scroll-behavior: smooth;
}

.font-serif {
  font-family: 'Playfair Display', serif;
}

.font-body {
  font-family: 'Lato', sans-serif;
}
</style>