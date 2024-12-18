import React, { useState } from 'react';
import { Book, Code, Users, Award, MessageSquare, Globe } from 'lucide-react';

const Portfolio = () => {
  const [activeTab, setActiveTab] = useState('projects');

  const navigationItems = [
    { id: 'projects', label: 'Projects', icon: Code },
    { id: 'leadership', label: 'Leadership', icon: Users },
    { id: 'speaking', label: 'Speaking', icon: MessageSquare },
    { id: 'research', label: 'Research', icon: Book },
    { id: 'skills', label: 'Skills', icon: Award },
  ];

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
  ];

  const leadership = [
    {
      title: "AI-Plans Team Leadership",
      description: "Led and grew a team of 20+ developers, including recruiting 4 senior developers.",
      achievements: [
        "Organized multiple successful critique-a-thons",
        "Managed project workflow using ClickUp and Kanban",
        "Led research initiatives in mechanistic interpretability"
      ]
    },
    {
      title: "Event Organization",
      description: "Organized and led multiple AI safety events and workshops.",
      achievements: [
        "Critique-a-thons with expert judges",
        "AI research workshops",
        "Local meetups and study groups"
      ]
    }
  ];

  const speaking = [
    {
      title: "University Speaking",
      events: [
        "University of Victoria's AI Ethics Society Event",
        "Ravensbourne University London",
        "VAISU (Virtual AI Safety Unconference)"
      ]
    }
  ];

  const research = [
    {
      title: "Mechanistic Interpretability",
      description: "Leading research on probing LLMs with classifiers to compare internals with SALAD benchmark scores.",
    }
  ];

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
  };

  const renderContent = () => {
    switch (activeTab) {
      case 'projects':
        return (
          <div className="space-y-6">
            {projects.map((project, index) => (
              <div key={index} className="bg-white p-6 rounded-lg shadow-md">
                <h3 className="text-xl font-semibold mb-2">{project.title}</h3>
                <p className="text-gray-600 mb-4">{project.description}</p>
                <ul className="list-disc pl-5 space-y-1">
                  {project.highlights.map((highlight, i) => (
                    <li key={i} className="text-gray-700">{highlight}</li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        );

      case 'leadership':
        return (
          <div className="space-y-6">
            {leadership.map((item, index) => (
              <div key={index} className="bg-white p-6 rounded-lg shadow-md">
                <h3 className="text-xl font-semibold mb-2">{item.title}</h3>
                <p className="text-gray-600 mb-4">{item.description}</p>
                <ul className="list-disc pl-5 space-y-1">
                  {item.achievements.map((achievement, i) => (
                    <li key={i} className="text-gray-700">{achievement}</li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        );

      case 'speaking':
        return (
          <div className="bg-white p-6 rounded-lg shadow-md">
            <h3 className="text-xl font-semibold mb-4">Speaking Engagements</h3>
            <ul className="list-disc pl-5 space-y-2">
              {speaking[0].events.map((event, index) => (
                <li key={index} className="text-gray-700">{event}</li>
              ))}
            </ul>
          </div>
        );

      case 'research':
        return (
          <div className="bg-white p-6 rounded-lg shadow-md">
            <h3 className="text-xl font-semibold mb-2">{research[0].title}</h3>
            <p className="text-gray-600">{research[0].description}</p>
          </div>
        );

      case 'skills':
        return (
          <div className="space-y-6">
            <div className="bg-white p-6 rounded-lg shadow-md">
              <h3 className="text-xl font-semibold mb-4">Technical Skills</h3>
              <div className="flex flex-wrap gap-2">
                {skills.technical.map((skill, index) => (
                  <span key={index} className="bg-blue-100 text-blue-800 px-3 py-1 rounded-full">
                    {skill}
                  </span>
                ))}
              </div>
            </div>
            <div className="bg-white p-6 rounded-lg shadow-md">
              <h3 className="text-xl font-semibold mb-4">Languages</h3>
              <div className="flex flex-wrap gap-2">
                {skills.languages.map((language, index) => (
                  <span key={index} className="bg-green-100 text-green-800 px-3 py-1 rounded-full">
                    {language}
                  </span>
                ))}
              </div>
            </div>
            <div className="bg-white p-6 rounded-lg shadow-md">
              <h3 className="text-xl font-semibold mb-4">Other Skills</h3>
              <div className="flex flex-wrap gap-2">
                {skills.other.map((skill, index) => (
                  <span key={index} className="bg-purple-100 text-purple-800 px-3 py-1 rounded-full">
                    {skill}
                  </span>
                ))}
              </div>
            </div>
          </div>
        );

      default:
        return null;
    }
  };

  return (
    <div className="min-h-screen bg-gray-100">
      <header className="bg-white shadow-md">
        <div className="max-w-5xl mx-auto px-4 py-6">
          <h1 className="text-3xl font-bold text-gray-900">Kabir Kumar</h1>
          <p className="text-gray-600 mt-2">
            AI Safety Researcher & Technical Lead
          </p>
        </div>
      </header>

      <nav className="bg-white shadow-sm mt-1">
        <div className="max-w-5xl mx-auto px-4">
          <div className="flex space-x-4">
            {navigationItems.map((item) => {
              const Icon = item.icon;
              return (
                <button
                  key={item.id}
                  onClick={() => setActiveTab(item.id)}
                  className={`flex items-center px-3 py-2 text-sm font-medium rounded-md ${
                    activeTab === item.id
                      ? 'text-blue-600 bg-blue-50'
                      : 'text-gray-600 hover:text-gray-900 hover:bg-gray-50'
                  }`}
                >
                  <Icon className="w-4 h-4 mr-2" />
                  {item.label}
                </button>
              );
            })}
          </div>
        </div>
      </nav>

      <main className="max-w-5xl mx-auto px-4 py-8">
        {renderContent()}
      </main>
    </div>
  );
};

export default Portfolio;
