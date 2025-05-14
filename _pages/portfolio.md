---
layout: default
permalink: /portfolio/
title: portfolio
nav: true
nav_order: 2
---

<div class="portfolio">
  <!-- Header Section -->
  <div class="header-section">
    <h1>Content Portfolio</h1>
    <p class="subtitle">Technical writing and content management focused on AI, ML, and emerging technologies</p>
  </div>


  <!-- Companies Grid -->
  <div class="companies-grid">
    <!-- Turing Post -->
    <div class="company-container">
      <div class="company-header">
        <h2>Turing Post</h2>
        <p>Writing about foundation models, LLMs, prompting and other research concepts long before it became mainstream.</p>
      </div>

      <div class="content-sections">
        <!-- AI 101 Series -->
        <div class="section-container">
          <div class="section-header">
            <h3>AI 101 Series</h3>
            <p>Clear explanations of complex AI concepts in plain English</p>
          </div>
          
          <div class="cards-grid">
            {% for content in site.data.portfolio.turingpost.technical %}
            <div class="content-card variant-1">
              <h4>{{ content.title }}</h4>
              <p>{{ content.description }}</p>
              <div class="card-meta">
                <span class="date">{{ content.date }}</span>
                <span class="author">{{ content.author }}</span>
              </div>
              <a href="{{ content.link }}" class="read-more" target="_blank">READ ARTICLE →</a>
            </div>
            {% endfor %}
          </div>
        </div>

        <!-- FMOps Series -->
        <div class="section-container">
          <div class="section-header">
            <h3>{{ site.data.portfolio.turingpost.fmops_series.title }}</h3>
            <p>{{ site.data.portfolio.turingpost.fmops_series.description }}</p>
          </div>
          
          <div class="cards-grid">
            {% for article in site.data.portfolio.turingpost.fmops_series.articles %}
            <div class="content-card variant-2">
              <span class="token-number">{{ article.title | split: ":" | first }}</span>
              <h4>{{ article.title | split: ":" | last }}</h4>
              <p>{{ article.description }}</p>
              <div class="card-meta">
                <span class="date">{{ article.date }}</span>
                <span class="author">{{ article.author }}</span>
              </div>
              <a href="{{ article.link }}" class="read-more" target="_blank">READ ARTICLE →</a>
            </div>
            {% endfor %}
          </div>
        </div>

        <!-- Historical Series -->
        <div class="section-container">
          <div class="section-header">
            <h3>Historical Series</h3>
            <p>Comprehensive exploration of AI evolution through different domains</p>
          </div>
          
          <div class="cards-grid">
            {% for article in site.data.portfolio.turingpost.historical_series %}
            <div class="content-card variant-3">
              <h4>{{ article.title }}</h4>
              <p>{{ article.description }}</p>
              <div class="card-meta">
                <span class="date">{{ article.date }}</span>
                <span class="author">{{ article.authors | default: article.author }}</span>
              </div>
              <a href="{{ article.link }}" class="read-more" target="_blank">READ ARTICLE →</a>
            </div>
            {% endfor %}
          </div>
        </div>

        <!-- Company Profiles -->
        <div class="section-container">
          <div class="section-header">
            <h3>Company Profiles</h3>
            <p>Deep dives into innovative AI companies shaping the industry</p>
          </div>
          
          <div class="cards-grid">
            {% for profile in site.data.portfolio.turingpost.company_profiles %}
            <div class="content-card variant-4">
              <h4>{{ profile.title }}</h4>
              <p>{{ profile.description }}</p>
              <div class="card-meta">
                <span class="date">{{ profile.date }}</span>
                <span class="author">{{ profile.authors | default: profile.author }}</span>
              </div>
              <a href="{{ profile.link }}" class="read-more" target="_blank">READ ARTICLE →</a>
            </div>
            {% endfor %}
          </div>
        </div>

        <!-- Short Notes -->
        <div class="section-container">
          <div class="section-header">
            <h3>Quick Insights</h3>
            <p>Concise observations on AI trends, challenges, and developments</p>
          </div>
          
          <div class="notes-grid">
            {% for note in site.data.portfolio.turingpost.short_notes %}
            <a href="{{ note.link }}" class="note-card" target="_blank">
              <span class="tag {{ note.tag | downcase }}">{{ note.tag }}</span>
              <p>{{ note.content }}</p>
              <span class="note-date">{{ note.date }}</span>
            </a>
            {% endfor %}
          </div>
        </div>
      </div>
    </div>

    <!-- Additional companies can be added here following the same structure -->
  </div>
</div>

<style>
/* Base Styles */
.portfolio {
  max-width: 1400px;
  margin: 0 auto;
  padding: 2rem;
}

/* Header Section */
.header-section {
  text-align: center;
  margin-bottom: 4rem;
}

.header-section h1 {
  font-size: 2.5rem;
  color: var(--global-theme-color);
  margin-bottom: 1rem;
}

.header-section .subtitle {
  font-size: 1.2rem;
  color: var(--global-text-color);
}

/* Social Media Section */
.social-section {
  margin-bottom: 4rem;
}

.tweet-embeds {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  justify-items: center;
}

/* Companies Grid */
.companies-grid {
  display: grid;
  gap: 4rem;
}

.company-container {
  background: var(--global-bg-color);
  border-radius: 12px;
  padding: 2rem;
}

.company-header {
  text-align: center;
  margin-bottom: 3rem;
}

.company-header h2 {
  font-size: 2.2rem;
  color: var(--global-theme-color);
  margin-bottom: 1rem;
}

/* Content Sections */
.content-sections {
  display: grid;
  gap: 3rem;
}

/* Section Containers */
.section-container {
  margin-bottom: 2rem;
}

.section-header {
  text-align: center;
  margin-bottom: 2rem;
}

.section-header h3 {
  font-size: 1.8rem;
  color: var(--global-theme-color);
  margin-bottom: 0.5rem;
}

.section-header p {
  color: var(--global-text-color);
}

/* Cards Grid */
.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}

/* Base Card Styles */
.content-card {
  background: white;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
  display: flex;
  flex-direction: column;
}

.content-card h4 {
  font-size: 1.3rem;
  margin-bottom: 1rem;
  color: var(--global-theme-color);
}

.content-card p {
  color: var(--global-text-color);
  line-height: 1.6;
  margin-bottom: 1.5rem;
  flex-grow: 1;
}

.card-meta {
  display: flex;
  justify-content: space-between;
  font-size: 0.9rem;
  color: var(--global-text-color-light);
  margin-bottom: 1.5rem;
}

.read-more {
  color: var(--global-theme-color);
  text-decoration: none;
  font-weight: 500;
  letter-spacing: 0.5px;
}

/* Card Variants */
.variant-1 {
  border-top: 3px solid #9C27B0;
}

.variant-2 {
  border-left: 3px solid #2196F3;
}

.variant-3 {
  border-bottom: 3px solid #4CAF50;
}

.variant-4 {
  border-right: 3px solid #FF9800;
}

.token-number {
  font-size: 0.9rem;
  color: var(--global-theme-color);
  margin-bottom: 0.5rem;
  display: block;
}

/* Notes Grid */
.notes-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.5rem;
}

.note-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column;
}

.note-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}

.note-date {
  margin-top: auto;
  font-size: 0.9rem;
  color: var(--global-text-color-light);
}

.tag {
  display: inline-block;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.85rem;
  color: white;
  margin-bottom: 1rem;
}

.tag.insight { background: #9C27B0; }
.tag.trend { background: #4CAF50; }
.tag.challenge { background: #F44336; }
.tag.privacy { background: #2196F3; }

/* Responsive Design */
@media (max-width: 768px) {
  .portfolio {
    padding: 1rem;
  }
  
  .cards-grid,
  .notes-grid {
    grid-template-columns: 1fr;
  }
  
  .header-section h1 {
    font-size: 2rem;
  }

  .company-container {
    padding: 1rem;
  }

  .company-header h2 {
    font-size: 1.8rem;
  }

  .section-header h3 {
    font-size: 1.5rem;
  }

  .tweet-embeds {
    grid-template-columns: 1fr;
  }
}
</style>

<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
