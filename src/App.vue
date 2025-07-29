<template>
  <div class="min-h-screen">
    <!-- Navigation -->
    <nav
      class="fixed w-full z-50 bg-slate-900/80 backdrop-blur-lg border-b border-white/10"
    >
      <div class="container mx-auto px-4 sm:px-6 py-4">
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-2">
            <img src="/logo.png" class="w-14 sm:w-20 h-auto" />
            <a
              href="#"
              class="text-xl sm:text-2xl font-bold bg-gradient-to-r from-[#FF9766] to-[#FF6062] bg-clip-text text-transparent"
            >
              {{ "Portfolio".toUpperCase() }}
            </a>
          </div>
          <div class="hidden md:flex space-x-6 sm:space-x-8">
            <a
              v-for="link in ['Home', 'Work', 'Projects', 'Contact']"
              :key="link"
              :href="'#' + link.toLowerCase()"
              class="nav-link"
            >
              {{ link }}
            </a>
          </div>
          <!-- Mobile menu button -->
          <div class="md:hidden">
            <button
              @click="showMenu = !showMenu"
              class="text-white focus:outline-none"
            >
              <svg width="28" height="28" fill="none" stroke="currentColor">
                <path
                  d="M4 8h20M4 16h20"
                  stroke-width="2"
                  stroke-linecap="round"
                />
              </svg>
            </button>
          </div>
        </div>
        <!-- Mobile menu -->
        <div v-if="showMenu" class="md:hidden mt-2 flex flex-col space-y-2">
          <a
            v-for="link in ['Home', 'Work', 'Projects', 'Contact']"
            :key="link"
            :href="'#' + link.toLowerCase()"
            class="nav-link"
            @click="showMenu = false"
          >
            {{ link }}
          </a>
        </div>
      </div>
    </nav>
    <!-- Hero Section -->
    <section
      id="home"
      class="relative min-h-screen flex flex-col md:flex-row pt-24 md:pt-0"
    >
      <!-- Animated background elements -->
      <div class="fixed inset-0 overflow-hidden pointer-events-none">
        <div
          class="fixed -top-40 -right-40 w-60 sm:w-80 h-60 sm:h-80 bg-gradient-to-r from-[#FF9766] to-[#FF6062] rounded-full filter blur-3xl animate-pulse-slow"
        ></div>
        <div
          class="fixed -bottom-40 -left-40 w-60 sm:w-80 h-60 sm:h-80 bg-gradient-to-r from-[#FF9766] to-[#FF6062] rounded-full filter blur-3xl animate-pulse-slow"
          style="animation-delay: 2s"
        ></div>
      </div>
      <div
        class="container mx-auto px-4 sm:px-6 relative flex flex-col md:flex-row justify-between w-full"
      >
        <!-- Left: Profile Information -->
        <div
          class="w-full md:w-1/2 space-y-8 md:sticky md:top-0 md:h-screen md:mr-28 flex flex-col justify-center items-center md:items-start pt-8 md:pt-0"
        >
          <h1
            class="text-2xl sm:text-3xl md:text-5xl font-bold leading-tight text-center md:text-left w-full flex justify-center"
          >
            Vincent Vullag
          </h1>
          <div
            class="relative hidden md:flex flex-col items-center justify-center w-full"
          >
            <div
              class="absolute inset-0 bg-gradient-to-r from-[#FF9766]/20 to-[#FF6062]/20 rounded-full filter blur-3xl"
              style="z-index: -1"
            ></div>
            <div class="flex justify-center w-full">
              <img
                src="/avatar.png"
                alt="Profile"
                class="relative w-32 sm:w-48 h-32 sm:h-48 object-cover rounded-full border-4 border-white/20 animate-float"
              />
            </div>
            <div
              class="text-center mt-4 flex justify-center items-center gap-4 text-lg w-full"
            >
              <a
                href="your-resume-link.pdf"
                target="_blank"
                class="text-white hover:text-blue-400 transition-colors duration-300 ease-in-out"
                >Resume</a
              >
              <span class="text-gray-400">|</span>
              <a
                href="https://github.com/vullagvs26"
                target="_blank"
                class="text-white hover:text-blue-400 transition-colors duration-300 ease-in-out"
                >GitHub</a
              >
              <span class="text-gray-400">|</span>
              <a
                href="https://www.linkedin.com/in/vullagvincent/"
                target="_blank"
                class="text-white hover:text-blue-400 transition-colors duration-300 ease-in-out"
                >LinkedIn</a
              >
            </div>
            <div class="text-center mt-4 w-full">
              <a
                class="text-2xl font-bold bg-gradient-to-r from-[#FF9766] to-[#FF6062] bg-clip-text text-transparent"
                >hello</a
              >
            </div>
          </div>
          <!-- Show avatar and links on mobile -->
          <div class="md:hidden flex flex-col items-center space-y-2">
            <img
              src="/avatar.png"
              alt="Profile"
              class="w-24 h-24 object-cover rounded-full border-4 border-white/20 animate-float"
            />
            <div class="flex justify-center items-center gap-2 text-base">
              <a
                href="your-resume-link.pdf"
                target="_blank"
                class="text-white hover:text-blue-400"
                >Resume</a
              >
              <span class="text-gray-400">|</span>
              <a
                href="https://github.com/vullagvs26"
                target="_blank"
                class="text-white hover:text-blue-400"
                >GitHub</a
              >
              <span class="text-gray-400">|</span>
              <a
                href="https://www.linkedin.com/in/vullagvincent/"
                target="_blank"
                class="text-white hover:text-blue-400"
                >LinkedIn</a
              >
            </div>
          </div>
          <p
            class="text-base sm:text-xl text-gray-300 leading-relaxed text-center md:text-left"
          >
            Experienced Full-Stack Web Developer with a strong foundation in
            HTML, Tailwind CSS, JavaScript, and frameworks like Vue.js and
            Laravel. Proficient in PHP, database management using MySQL
            Workbench, pgAdmin (PostgreSQL), and Oracle.
          </p>
          <p
            class="text-base sm:text-xl text-gray-300 leading-relaxed text-center md:text-left"
          >
            Skilled in building responsive, user-friendly applications and
            integrating with complex backend systems. Also experienced in Power
            Apps development, CRM systems, and front-end troubleshooting for
            Microsoft Dynamics 365 and SAP. Versatile in UI/UX design with tools
            like Figma, ensuring intuitive and polished user experiences.
          </p>
        </div>
        <!-- Right: Scrollable Content -->
        <div id="about" class="w-full md:w-1/2 h-auto mt-12 md:mt-48">
          <!-- Profile Views Counter -->
          <div class="mb-4 text-center md:text-left">
            <img
              src="https://komarev.com/ghpvc/?username=vullagvs26&label=Profile%20views&color=0e75b6&style=flat"
              alt="vullagvs26"
            />
          </div>
          <h2 class="text-xl sm:text-2xl font-bold mb-4">About Me</h2>
          <p class="text-base sm:text-lg text-gray-300 leading-relaxed">
            Hi, I'm Vincent Sanchez Vullag, 25 years old, and a graduate of
            National University Laguna with a degree in Computer Science. I’m
            passionate about Front-End Development and UI Design—throughout my
            college years, I always gravitated toward website projects, enjoying
            the creative and technical aspects of building user-friendly
            interfaces.
          </p>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-6">
            <div
              v-for="(value, key) in stats"
              :key="key"
              class="glass-card p-4 text-center"
            >
              <div
                class="text-2xl sm:text-3xl font-bold bg-gradient-to-r from-[#FF9766] to-[#FF6062] bg-clip-text text-transparent"
              >
                {{ value }}
              </div>
              <div class="text-xs sm:text-sm text-gray-400 mt-2">{{ key }}</div>
            </div>
          </div>
          <!-- Technical Expertise Section -->
          <div id="work" class="space-y-8 mt-12">
            <h3 class="text-xl sm:text-2xl font-bold">Technical Expertise</h3>
            <div class="space-y-6">
              <div
                v-for="skill in skills"
                :key="skill.name"
                class="glass-card p-4"
              >
                <div class="flex justify-between mb-2">
                  <span class="font-medium">{{ skill.name }}</span>
                  <span class="text-[#FF6062]">{{ skill.level }}%</span>
                </div>
                <div class="h-2 bg-white/10 rounded-full overflow-hidden">
                  <div
                    class="h-full bg-gradient-to-r from-[#FF9766] to-[#FF6062] rounded-full transition-all duration-500"
                    :style="{ width: skill.level + '%' }"
                  ></div>
                </div>
                <div class="flex space-x-3 mt-3">
                  <component
                    v-for="(icon, index) in skill.icons"
                    :key="index"
                    :is="icon"
                    class="w-6 h-6 text-white"
                  />
                </div>
              </div>
            </div>
          </div>
          <!-- Projects Section -->
          <div id="projects" class="py-10 sm:py-20">
            <h2 class="section-title text-center">Featured Projects</h2>
            <swiper
              :slidesPerView="1"
              :breakpoints="{
                640: { slidesPerView: 1 },
                768: { slidesPerView: 2 },
              }"
              :spaceBetween="20"
              :keyboard="{ enabled: true }"
              :pagination="{ clickable: true }"
              :navigation="true"
              :modules="[Keyboard, Pagination, Navigation]"
              class="mySwiper"
            >
              <swiper-slide
                v-for="project in projects"
                :key="project.title"
                class="group glass-card overflow-hidden"
              >
                <div class="relative overflow-hidden">
                  <img
                    :src="project.image"
                    :alt="project.title"
                    class="w-full h-40 sm:h-60 object-cover transition-transform duration-500 group-hover:scale-110"
                  />
                  <div
                    class="absolute inset-0 bg-gradient-to-t from-dark/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"
                  ></div>
                </div>
                <div class="p-4 sm:p-6 space-y-2 sm:space-y-4">
                  <h3 class="text-lg sm:text-xl font-bold">
                    {{ project.title }}
                  </h3>
                  <p class="text-gray-300 text-sm sm:text-base">
                    {{ project.description }}
                  </p>
                  <div class="flex flex-wrap gap-2">
                    <span
                      v-for="tech in project.technologies"
                      :key="tech"
                      class="tech-pill"
                      >{{ tech }}</span
                    >
                  </div>
                  <div class="pt-2 sm:pt-4 flex space-x-2 sm:space-x-4">
                    <a
                      :href="project.demo"
                      class="btn-primary text-xs sm:text-sm"
                      >Live Demo</a
                    >
                    <a
                      :href="project.github"
                      class="btn-outline text-xs sm:text-sm"
                      >GitHub</a
                    >
                  </div>
                </div>
              </swiper-slide>
            </swiper>
          </div>
          <!-- Contact Section -->
          <div id="contact" class="py-8 sm:py-10">
            <h2 class="section-title text-center">Get In Touch</h2>
            <div class="max-w-full sm:max-w-3xl mx-auto glass-card p-4 sm:p-8">
              <form class="space-y-4 sm:space-y-6">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-6">
                  <div>
                    <label class="block text-gray-300 mb-2">Name</label>
                    <input
                      type="text"
                      class="input-field"
                      placeholder="John Doe"
                    />
                  </div>
                  <div>
                    <label class="block text-gray-300 mb-2">Email</label>
                    <input
                      type="email"
                      class="input-field"
                      placeholder="john@example.com"
                    />
                  </div>
                </div>
                <div>
                  <label class="block text-gray-300 mb-2">Subject</label>
                  <input
                    type="text"
                    class="input-field"
                    placeholder="Project Inquiry"
                  />
                </div>
                <div>
                  <label class="block text-gray-300 mb-2">Message</label>
                  <textarea
                    rows="4"
                    class="input-field"
                    placeholder="Your message here..."
                  ></textarea>
                </div>
                <button type="submit" class="btn-primary w-full">
                  Send Message
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Footer -->
    <footer class="py-8 sm:py-12 border-t border-white/10">
      <div class="container mx-auto px-4 sm:px-6">
        <div class="flex flex-col md:flex-row justify-around gap-8 md:gap-0">
          <div>
            <h3 class="text-lg sm:text-xl font-bold mb-4">Let's Connect</h3>
            <div class="flex space-x-4">
              <a
                v-for="social in socials"
                :key="social.name"
                :href="social.url"
                target="_blank"
                class="w-10 h-10 rounded-full glass-card flex items-center justify-center hover:bg-white/20 transition-colors"
              >
                <component :is="social.icon" class="w-6 h-6 text-white" />
              </a>
            </div>
          </div>
          <div>
            <h3 class="text-lg sm:text-xl font-bold mb-4">Quick Links</h3>
            <div class="space-y-2">
              <a
                v-for="link in ['Home', 'About', 'Projects', 'Contact']"
                :key="link"
                :href="'#' + link.toLowerCase()"
                class="block text-gray-300 hover:text-white transition-colors"
              >
                {{ link }}
              </a>
            </div>
          </div>
          <div>
            <h3 class="text-lg sm:text-xl font-bold mb-4">Contact Info</h3>
            <div class="space-y-2 text-gray-300 text-sm sm:text-base">
              <p>vincentvullag@gmail.com</p>
              <p>Calamba City, Laguna Philippines</p>
            </div>
          </div>
        </div>
        <div
          class="mt-8 sm:mt-12 pt-4 sm:pt-8 border-t border-white/10 text-center text-gray-400 text-xs sm:text-base"
        >
          <p>&copy; 2024 Vincent Vullag. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { Figma, Code, Video, Database } from "lucide-vue-next";
import { Github, Linkedin, Facebook, Instagram } from "lucide-vue-next";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";
import "swiper/css/navigation";
import "./style.css";
import { Keyboard, Pagination, Navigation } from "swiper/modules";

const showMenu = ref(false);

const stats = {
  "Projects Completed": "50+",
  "Years Experience": "5+",
  "Happy Clients": "30+",
  "Awards Won": "10+",
};

const skills = [
  { name: "UI/UX Design", level: 90, icons: [Figma] },
  { name: "System Development", level: 85, icons: [Code] },
  { name: "Video Editing", level: 75, icons: [Video] },
  { name: "Data Analysis", level: 70, icons: [Database] },
];

const projects = [
  {
    title: "E-Commerce Platform",
    description:
      "A full-featured online shopping platform with real-time inventory management.",
    image: "/PORTFOLIO/coming-soon.png",
    technologies: ["Vue", "Node.js", "MongoDB"],
    demo: "#",
    github: "#",
  },
  {
    title: "Social Media Dashboard",
    description:
      "Analytics dashboard for social media management and monitoring.",
    image: "/PORTFOLIO/coming-soon.png",
    technologies: ["React", "GraphQL", "AWS"],
    demo: "#",
    github: "#",
  },
  {
    title: "AI Content Generator",
    description:
      "AI-powered platform for generating marketing content and copy.",
    image: "/PORTFOLIO/coming-soon.png",
    technologies: ["Python", "TensorFlow", "FastAPI"],
    demo: "#",
    github: "#",
  },
  {
    title: "AI Content Generator",
    description:
      "AI-powered platform for generating marketing content and copy.",
    image: "/PORTFOLIO/coming-soon.png",
    technologies: ["Python", "TensorFlow", "FastAPI"],
    demo: "#",
    github: "#",
  },
  {
    title: "AI Content Generator",
    description:
      "AI-powered platform for generating marketing content and copy.",
    image: "/PORTFOLIO/coming-soon.png",
    technologies: ["Python", "TensorFlow", "FastAPI"],
    demo: "#",
    github: "#",
  },
];

const socials = [
  { name: "GitHub", url: "https://github.com/vullagvs26", icon: Github },
  { name: "LinkedIn", url: "#", icon: Linkedin },
  { name: "Facebook", url: "#", icon: Facebook },
  { name: "Instagram", url: "#", icon: Instagram },
];
</script>

<style>
.swiper-button {
  background-color: rgb(255, 255, 255) !important;
}
.swiper-pagination-bullet {
  background-color: rgb(255, 255, 255) !important;
  opacity: 1;
}
.swiper-pagination-bullet-active {
  background-color: #eb8863 !important;
}
.swiper-button-prev,
.swiper-button-next {
  color: white !important;
}
.swiper-button-prev::after,
.swiper-button-next::after {
  font-size: 24px !important;
}
.swiper-button-prev,
.swiper-button-next {
  padding: 10px;
  border-radius: 50%;
}
</style>
