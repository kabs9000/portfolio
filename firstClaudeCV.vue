# Portfolio.vue
<script setup>
import { ref } from 'vue'

const activeTab = ref('projects')

const navigationItems = [
  { id: 'projects', label: 'Projects', icon: 'Code' },
  { id: 'events', label: 'Events', icon: 'Users' },
  { id: 'speaking', label: 'Speaking', icon: 'MessageSquare' },
  { id: 'research', label: 'Research', icon: 'Book' },
  { id: 'skills', label: 'Skills', icon: 'Award' },
]

const projects = [
  {
    title: "AI-Plans Platform",
    description: "Founded and led development of a platform for analyzing AI alignment plans. Led a team of 20+ developers and secured £5,270+ in funding.",
    highlights: [
      "Implemented in Vue.js, MySQL, and PocketBase",
      "Organized successful critique-a-thons with judges from DeepMind, MIRI, and MIT",
      "Designed critical user journeys and managed development using ClickUp"
    ]
  },
  {
    title: "Search Aggregator",
    description: "Built a custom search tool integrating DuckDuckGo API with Groq LLM for enhanced search results and summaries.",
    highlights: [
      "Integrated multiple APIs",
      "Implemented advanced result processing",
      "Created user-friendly interface"
    ]
  },
  {
    title: "Decoder Transformer",
    description: "Implemented a decoder-only transformer model following educational tutorials.",
    highlights: [
      "Built with PyTorch",
      "Focused on core transformer architecture",
      "Educational implementation"
    ]
  }
]

const events = [
  {
    title: "AI & Liability Ideathon (December 2024)",
    description: "Two-week event bringing together lawyers, researchers, and developers",
    details: [
      "Secured speakers including Gabriel Weil (Touro University) and Tzu Kit Chan (MATS)",
      "Structured team formation and idea development process",
      "Final presentation evening with peer review"
    ]
  },
  {
    title: "December 2023 Critique-a-thon",
    description: "High-profile event analyzing AI alignment research",
    details: [
      "Secured judges: Nate Soares (MIRI President), Ramana Kumar (ex-DeepMind)",
      "Additional judges: Dr. Peter S. Park (MIT), Charbel-Raphaël (EffiSciences)",
      "Teams critiqued recent papers including DeepMind's Nash Learning from Human Feedback",
      "Structured format with detailed judging criteria"
    ]
  },
  {
    title: "September 2023 Critique-a-thon",
    description: "Created debate-based format for deep analysis",
    details: [
      "Judges: Dr. Peter S. Park (MIT Tegmark lab), Charbel-Raphael Segerie (EffiSciences)",
      "Managed 10-30 active participants",
      "Published winning critiques on AI-Plans platform"
    ]
  },
  {
    title: "March 2023 Critique-a-thon",
    description: "Four-day structured event with $1000 prize pool",
    details: [
      "Judges: Ramana Kumar (DeepMind), Charbel-Raphaël Segerie (EffiSciences), Dr Peter S Park (MIT)",
      "Innovative debate partner system",
      "Presentation evening with comprehensive feedback"
    ]
  },
  {
    title: "AI Law-a-thon",
    description: "Policy development event bridging legal and technical perspectives",
    details: [
      "Created policy recommendations for machine unlearning",
      "Generated analysis of AI direct democracy implications",
      "Produced draft legislation for artificial image regulation",
      "Brought together legal experts and AI researchers"
    ]
  },
  {
    title: "AI Research Workshops",
    description: "Community education initiatives in AI safety",
    details: [
      "Organized 'AI Mech Interp Speedrun Meetup'",
      "Led workshop on automating mechanistic interpretation",
      "Taught neural network fundamentals to newcomers",
      "Hosted at local library for community engagement"
    ]
  }
]

const speaking = [
  {
    title: "University of Victoria's AI Ethics Society Event",
    description: "Speaker on AI Safety and AI-Plans",
  },
  {
    title: "Ravensbourne University London",
    description: "Presentation on AI-Plans and alignment research",
  },
  {
    title: "VAISU (Virtual AI Safety Unconference)",
    description: "Speaker on AI alignment research",
  }
]

const research = [
  {
    title: "Mechanistic Interpretability",
    description: "Leading research on probing LLMs with classifiers to compare internals with SALAD benchmark scores.",
    details: [
      "Developed novel testing methodologies",
      "Collaborated with international research team",
      "Working on publication of findings"
    ]
  },
  {
    title: "Feature Detection Guide",
    description: "Created comprehensive guide on finding features with premade sparse autoencoders (SAEs).",
    details: [
      "Detailed walkthrough of SAE usage with models",
      "Code examples for feature detection",
      "Best practices for analysis and visualization"
    ]
  },
  {
    title: "AI Safety Research",
    description: "Co-authored 'Broad Vulnerability Categories for AI Safety Plans'.",
    details: [
      "Comprehensive categorization of AI safety vulnerabilities",
      "Used in multiple critique-a-thons",
      "Referenced by AI safety researchers"
    ]
  }
]

const skills = {
  technical: [
    "Vue.js",
    "Python",
    "Git",
    "MySQL",
    "Redis",
    "PocketBase",
    "Basic PyTorch & NumPy"
  ],
  languages: [
    "English (Native)",
    "Hindi (Native)",
    "German (Fluent)"
  ],
  other: [
    "Project Management",
    "Team Leadership",
    "Event Organization",
    "Technical Writing"
  ]
}
</script>

<template>
  <div class="min-h-screen bg-gray-100">
    <!-- Header -->
    <header class="bg-white shadow-md">
      <div class="max-w-5xl mx-auto px-4 py-6">
        <h1 class="text-3xl font-bold text-gray-900">Kabir Kumar</h1>
        <p class="text-gray-600 mt-2">
          AI Safety Researcher & Technical Lead
        </p>
      </div>
    </header>

    <!-- Navigation -->
    <nav class="bg-white shadow-sm mt-1">
      <div class="max-w-5xl mx-auto px-4">
        <div class="flex space-x-4">
          <button
            v-for="item in navigationItems"
            :key="item.id"
            @click="activeTab = item.id"
            :class="[
              'flex items-center px-3 py-2 text-sm font-medium rounded-md',
              activeTab === item.id
                ? 'text-blue-600 bg-blue-50'
                : 'text-gray-600 hover:text-gray-900 hover:bg-gray-50'
            ]"
          >
            <span class="mr-2">
              <i :class="'pi pi-' + item.icon.toLowerCase()" />
            </span>
            {{ item.label }}
          </button>
        </div>
      </div>
    </nav>

    <!-- Main Content -->
    <main class="max-w-5xl mx-auto px-4 py-8">
      <!-- Projects -->
      <div v-if="activeTab === 'projects'" class="space-y-6">
        <div v-for="(project, index) in projects" :key="index" class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-2">{{ project.title }}</h3>
          <p class="text-gray-600 mb-4">{{ project.description }}</p>
          <ul class="list-disc pl-5 space-y-1">
            <li v-for="(highlight, i) in project.highlights" :key="i" class="text-gray-700">
              {{ highlight }}
            </li>
          </ul>
        </div>
      </div>

      <!-- Events -->
      <div v-if="activeTab === 'events'" class="space-y-6">
        <div v-for="(event, index) in events" :key="index" class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-2">{{ event.title }}</h3>
          <p class="text-gray-600 mb-4">{{ event.description }}</p>
          <ul class="list-disc pl-5 space-y-1">
            <li v-for="(detail, i) in event.details" :key="i" class="text-gray-700">
              {{ detail }}
            </li>
          </ul>
        </div>
      </div>

      <!-- Speaking -->
      <div v-if="activeTab === 'speaking'" class="space-y-6">
        <div v-for="(talk, index) in speaking" :key="index" class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-2">{{ talk.title }}</h3>
          <p class="text-gray-600">{{ talk.description }}</p>
        </div>
      </div>

      <!-- Research -->
      <div v-if="activeTab === 'research'" class="space-y-6">
        <div v-for="(item, index) in research" :key="index" class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-2">{{ item.title }}</h3>
          <p class="text-gray-600 mb-4">{{ item.description }}</p>
          <ul class="list-disc pl-5 space-y-1">
            <li v-for="(detail, i) in item.details" :key="i" class="text-gray-700">
              {{ detail }}
            </li>
          </ul>
        </div>
      </div>

      <!-- Skills -->
      <div v-if="activeTab === 'skills'" class="space-y-6">
        <div class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-4">Technical Skills</h3>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="(skill, index) in skills.technical"
              :key="index"
              class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full"
            >
              {{ skill }}
            </span>
          </div>
        </div>
        <div class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-4">Languages</h3>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="(language, index) in skills.languages"
              :key="index"
              class="bg-green-100 text-green-800 px-3 py-1 rounded-full"
            >
              {{ language }}
            </span>
          </div>
        </div>
        <div class="bg-white p-6 rounded-lg shadow-md">
          <h3 class="text-xl font-semibold mb-4">Other Skills</h3>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="(skill, index) in skills.other"
              :key="index"
              class="bg-purple-100 text-purple-800 px-3 py-1 rounded-full"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped>
.card {
  background: #ffffff;
  padding: 2rem;
  border-radius: 10px;
  margin-bottom: 2rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
</style>