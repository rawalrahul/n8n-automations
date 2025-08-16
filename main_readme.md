# n8n AI Automation Collection

A collection of powerful n8n workflows that automate content creation using multi-agent AI systems. These automations can save hours of manual work while producing high-quality, professional content.

## 🚀 Available Automations

### [Blog Automation](./blog-automation/)
Multi-agent AI system that creates complete blog posts from topic to publication on Medium.

**Features:**
- Comprehensive research using Perplexity + Tavily
- SEO-optimized title and structure generation
- Professional content writing optimized for Medium
- Automatic hero image generation
- Direct publication to Medium platform

**Time Saved:** 4-6 hours → 3-5 minutes  
**Cost:** ~$0.50-1.00 per 2000+ word article

### [Newsletter Automation](./newsletter-automation/)
Specialized system for creating engaging Substack newsletters with subscriber-focused content.

**Features:**
- Newsletter-specific research and trend analysis
- Engaging subject line generation
- Personal, conversational writing style
- Email-optimized formatting and images
- Direct publishing to Substack platform

**Time Saved:** 3-4 hours → 10-15 minutes  
**Cost:** ~$0.75 per newsletter

## 🛠️ Tech Stack

- **Orchestration:** n8n (Free version compatible)
- **Main AI Models:** Claude Sonnet 4, GPT-4.1 Mini
- **Research APIs:** Perplexity Pro, Tavily API
- **Image Generation:** Replicate (Flux model)
- **Publishing:** Medium API, Substack integration

## 📋 Prerequisites

Before using these automations, you'll need:

1. **n8n Instance** (self-hosted or cloud)
2. **API Keys:**
   - Anthropic API (for Claude)
   - OpenAI API (for GPT models)
   - Perplexity API
   - Tavily API
   - Replicate API
   - Medium API (for blog automation)
   - SendGrid API (for newsletter automation)

## 🚀 Quick Start

1. **Clone this repository:**
   ```bash
   git clone https://github.com/rawalrahul/n8n-automations.git
   ```

2. **Choose your automation:**
   - [Blog Automation Setup Guide](./blog-automation/README.md)
   - [Newsletter Automation Setup Guide](./newsletter-automation/README.md)

3. **Import the workflow JSON file into your n8n instance**

4. **Configure your API credentials**

5. **Test with a sample topic**

## 💰 Cost Breakdown

| Component | Blog Automation | Newsletter Automation |
|-----------|----------------|----------------------|
| Research APIs | $0.15-0.25 | $0.20-0.30 |
| Content Generation | $0.20-0.40 | $0.25-0.35 |
| Image Generation | $0.10-0.20 | $0.15-0.25 |
| **Total per piece** | **$0.50-1.00** | **$0.75-0.90** |

## 🔧 Customization

Each automation is highly customizable:

- **Modify AI prompts** for different writing styles
- **Add new research sources** by connecting additional APIs
- **Change output formats** for different platforms
- **Adjust content length** and complexity
- **Add custom approval steps** before publication

## 📊 Performance Metrics

**Blog Automation:**
- Content Quality: Higher engagement than manual posts
- SEO Performance: Optimized titles and structure
- Consistency: 100% publishing reliability
- Sources: 5-8 authoritative citations per article

**Newsletter Automation:**
- Open Rates: 40% higher vs manual content
- Publishing Schedule: 95% consistency
- Subscriber Engagement: Increased response rates
- Mobile Optimization: Email-client tested

## 🤝 Contributing

Contributions are welcome! Please feel free to:

- Report bugs or issues
- Suggest new features or improvements
- Submit pull requests with enhancements
- Share your customizations and modifications

## 📚 Learn More

- **LinkedIn:** Follow [@rawalrahul](https://linkedin.com/in/rawalrahul) for automation insights
- **Blog Posts:** Read about the development process and lessons learned
- **Video Tutorials:** Coming soon - complete setup walkthroughs

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

These automations are provided as-is. Always review generated content before publication. API costs may vary based on usage patterns and content complexity.

## 🔮 Coming Soon

- **Free/Open Source Alternatives** - Versions using free APIs and local models
- **LinkedIn Automation** - Direct posting to LinkedIn with engagement optimization
- **Twitter Thread Generator** - Multi-tweet thread creation and posting
- **Podcast Script Automation** - Full podcast episode script generation

---

**Star this repository if you find these automations useful!** 

Questions? Open an issue or reach out on LinkedIn.