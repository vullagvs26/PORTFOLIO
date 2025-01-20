<template>
  <div class="min-h-screen">
    <!-- Navigation -->
    <nav
      class="fixed w-full z-50 bg-slate-900/80 backdrop-blur-lg border-b border-white/10"
    >
      <div class="container mx-auto px-6 py-4">
        <div class="flex items-center justify-between">
          <div class="flex items-center justify-between">
            <img src="/logo.png" class="w-20 h-auto" />
            <a
              href="#"
              class="text-2xl font-bold bg-gradient-to-r from-[#FF9766] to-[#FF6062] bg-clip-text text-transparent"
            >
              {{ "Portfolio".toUpperCase() }}
            </a>
          </div>
          <div class="hidden md:flex space-x-8">
            <a
              v-for="link in ['Home', 'Work', 'Projects', 'Contact']"
              :key="link"
              :href="'#' + link.toLowerCase()"
              class="nav-link"
            >
              {{ link }}
            </a>
          </div>
        </div>
      </div>
    </nav>

    Hero Section
    <section id="home" class="relative min-h-screen flex items-center">
      <!-- Animated background elements -->
      <div class="absolute inset-0 overflow-hidden">
        <div
          class="absolute -top-40 -right-40 w-80 h-80 bg-gradient-to-r from-[#FF9766] to-[#FF6062] rounded-full filter blur-3xl animate-pulse-slow"
        ></div>
        <div
          class="absolute -bottom-40 -left-40 w-80 h-80 bg-gradient-to-r from-[#FF9766] to-[#FF6062] rounded-full filter blur-3xl animate-pulse-slow"
          style="animation-delay: 2s"
        ></div>
      </div>

      <div class="container mx-auto px-6 relative">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="space-y-8">  
            <h1 class="text-3xl md:text-5xl font-bold leading-tight text-center">
             Vincent  Vullag     
            </h1>
            <div class="relative hidden md:block">
            <div
             class="absolute inset-0 bg-gradient-to-r from-[#FF9766]/20 to-[#FF6062]/20 rounded-full filter blur-3xl"
            ></div>
            <img
              src="/avatar.png"
              alt="Profile"
              class="relative w-48 h-48 object-cover rounded-full border-4 border-white/20 animate-float mx-auto"
            />
            <div>
            <div>
              
            <a class="text-2xl font-bold bg-gradient-to-r from-[#FF9766] to-[#FF6062] bg-clip-text text-transparent text-center">
            hello
            </a>
            </div>
            
            </div>
          </div>
            <p class="text-xl text-gray-300 leading-relaxed">
             Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus suscipit, 
             lorem non tristique faucibus, odio justo fermentum nisi, ut cursus sapien enim ac felis. 
             Fusce dictum libero et mauris blandit, eu tincidunt libero pharetra. <br><br> 
             
             Sed vehicula, lacus at egestas facilisis, metus lectus gravida erat, quis viverra 
             Curabitur nec erat vitae risus facilisis commodo. Nam id eros in nisi pharetra venenatis vel nec ligula. 
             Proin gravida, velit ac feugiat scelerisque, enim libero aliquam eros, vitae malesuada ligula lorem sit amet urna. 
             Suspendisse potenti. Donec eget metus a nisl consectetur vulputate eget sed mi.
            </p>

          </div>
         
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20">
      <div class="container mx-auto px-6">
        <h2 class="section-title text-center">About Me</h2>
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div class="glass-card p-8 space-y-6">
            <p class="text-lg text-gray-300 leading-relaxed">
              With over 5 years of experience in web development, I specialize in creating
              scalable and performant applications. My passion lies in combining beautiful
              design with clean, efficient code.
            </p>
            <div class="grid grid-cols-2 gap-4">
              <div
                v-for="(value, key) in stats"
                :key="key"
                class="glass-card p-4 text-center"
              >
                <div
                 class="text-3xl font-bold bg-gradient-to-r from-[#FF9766] to-[#FF6062] bg-clip-text text-transparent"
                >
                  {{ value }}
                </div>
                <div class="text-sm text-gray-400 mt-2">{{ key }}</div>
              </div>
            </div>
          </div>
          <div class="space-y-8">
            <h3 class="text-2xl font-bold">Technical Expertise</h3>
            <div class="space-y-6">
              <div v-for="skill in skills" :key="skill.name" class="glass-card p-4">
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
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="py-20">
      <div class="container mx-auto px-6">
        <h2 class="section-title text-center">Featured Projects</h2>
        <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div
            v-for="project in projects"
            :key="project.title"
            class="group glass-card overflow-hidden"
          >
            <div class="relative overflow-hidden">
              <img
                :src="project.image"
                :alt="project.title"
                class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-gradient-to-t from-dark/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              ></div>
            </div>
            <div class="p-6 space-y-4">
              <h3 class="text-xl font-bold">{{ project.title }}</h3>
              <p class="text-gray-300">{{ project.description }}</p>
              <div class="flex flex-wrap gap-2">
                <span
                  v-for="tech in project.technologies"
                  :key="tech"
                  class="tech-pill"
                  >{{ tech }}</span
                >
              </div>
              <div class="pt-4 flex space-x-4">
                <a :href="project.demo" class="btn-primary text-sm">Live Demo</a>
                <a :href="project.github" class="btn-outline text-sm">GitHub</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20">
      <div class="container mx-auto px-6">
        <h2 class="section-title text-center">Get In Touch</h2>
        <div class="max-w-3xl mx-auto glass-card p-8">
          <form class="space-y-6">
            <div class="grid md:grid-cols-2 gap-6">
              <div>
                <label class="block text-gray-300 mb-2">Name</label>
                <input type="text" class="input-field" placeholder="John Doe" />
              </div>
              <div>
                <label class="block text-gray-300 mb-2">Email</label>
                <input type="email" class="input-field" placeholder="john@example.com" />
              </div>
            </div>
            <div>
              <label class="block text-gray-300 mb-2">Subject</label>
              <input type="text" class="input-field" placeholder="Project Inquiry" />
            </div>
            <div>
              <label class="block text-gray-300 mb-2">Message</label>
              <textarea
                rows="4"
                class="input-field"
                placeholder="Your message here..."
              ></textarea>
            </div>
            <button type="submit" class="btn-primary w-full">Send Message</button>
          </form>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="py-12 border-t border-white/10">
      <div class="container mx-auto px-6">
        <div class="grid md:grid-cols-3 gap-8">
          <div>
            <h3 class="text-xl font-bold mb-4">Let's Connect</h3>
            <div class="flex space-x-4">
              <a
                v-for="social in socials"
                :key="social.name"
                :href="social.url"
                class="w-10 h-10 rounded-full glass-card flex items-center justify-center hover:bg-white/20 transition-colors"
              >
                {{ social.name[0] }}
              </a>
            </div>
          </div>
          <div>
            <h3 class="text-xl font-bold mb-4">Quick Links</h3>
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
          .
          <div>
            <h3 class="text-xl font-bold mb-4">Contact Info</h3>
            <div class="space-y-2 text-gray-300">
              <p>contact@example.com</p>
              <p>San Francisco, CA</p>
            </div>
          </div>
        </div>
        <div class="mt-12 pt-8 border-t border-white/10 text-center text-gray-400">
          <p>&copy; 2024 Your Name. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
const stats = {
  "Projects Completed": "50+",
  "Years Experience": "5+",
  "Happy Clients": "30+",
  "Awards Won": "10+",
};

const skills = [
  { name: "Frontend Development", level: 90 },
  { name: "Backend Development", level: 85 },
  { name: "UI/UX Design", level: 75 },
  { name: "DevOps", level: 70 },
];

const projects = [
  {
    title: "E-Commerce Platform",
    description:
      "A full-featured online shopping platform with real-time inventory management.",
    image: "https://picsum.photos/400/250?random=1",
    technologies: ["Vue", "Node.js", "MongoDB"],
    demo: "#",
    github: "#",
  },
  {
    title: "Social Media Dashboard",
    description: "Analytics dashboard for social media management and monitoring.",
    image: "https://picsum.photos/400/250?random=2",
    technologies: ["React", "GraphQL", "AWS"],
    demo: "#",
    github: "#",
  },
  {
    title: "AI Content Generator",
    description: "AI-powered platform for generating marketing content and copy.",
    image: "https://picsum.photos/400/250?random=3",
    technologies: ["Python", "TensorFlow", "FastAPI"],
    demo: "#",
    github: "#",
  },
];

const socials = [
  { name: "GitHub", url: "https://github.com/vullagvs26" },
  { name: "LinkedIn", url: "#" },
  { name: "Twitter", url: "#" },
  { name: "Instagram", url: "#" },
];
</script>
