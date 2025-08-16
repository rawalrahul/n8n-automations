# Newsletter Automation - Substack Publishing Workflow

A specialized multi-agent AI system that creates engaging, subscriber-focused newsletters for Substack in 10-15 minutes instead of 3-4 hours of manual work.

## Overview

This workflow creates compelling newsletters optimized for email engagement and Substack's platform. The system focuses on personal, conversational content that drives subscriber retention and engagement.

## Architecture

### Agent System
- **Newsletter Research Agent** - Finds subscriber-worthy content and trends
- **Newsletter Structure Agent** - Creates engaging subject lines and email structure
- **Substack Writer Agent** - Writes personal, conversational newsletter content
- **Newsletter Visual Agent** - Generates email-optimized header images
- **Substack Format Agent** - Formats content for email and Substack platform
- **Publishing Coordinator** - Manages Substack publication process

### Tech Stack
- **Orchestration**: n8n workflow automation
- **Main LLM**: Claude Sonnet 4 (orchestrator)
- **Supporting Models**: GPT-4.1 Mini (specialized agents)
- **Research**: Perplexity Pro + Tavily APIs
- **Images**: Replicate (Flux model, 16:9 ratio)
- **Publishing**: Email to Substack + Webhook options

## Prerequisites

### Required API Keys

1. **Anthropic API** (Claude Sonnet 4)
   - Sign up at: https://console.anthropic.com/
   - Cost: ~$0.25-0.35 per newsletter

2. **OpenAI API** (GPT-4.1 Mini)
   - Sign up at: https://platform.openai.com/
   - Cost: ~$0.15-0.25 per newsletter

3. **Perplexity API**
   - Sign up at: https://docs.perplexity.ai/
   - Cost: ~$0.20-0.30 per newsletter

4. **Tavily API**
   - Sign up at: https://tavily.com/
   - Cost: ~$0.05-0.10 per newsletter

5. **Replicate API** (Image Generation)
   - Sign up at: https://replicate.com/
   - Cost: ~$0.15-0.25 per image

6. **SendGrid API** (Email Method - Optional)
   - Sign up at: https://sendgrid.com/
   - Cost: Free tier available

### Substack Setup
- Active Substack publication
- Substack email address for draft creation
- Publication URL and settings configured

## Installation

### 1. Import Workflow
1. Download `newsletter-workflow.json` from this repository
2. Open your n8n instance
3. Click "Import from File" and select the JSON file
4. The workflow will be imported with all nodes

### 2. Configure API Credentials

#### Anthropic (Claude)
1. Go to n8n Settings > Credentials
2. Add new credential type: "Anthropic API"
3. Enter your Anthropic API key

#### OpenAI (GPT)
1. Add credential type: "OpenAI API"
2. Enter your OpenAI API key

#### Perplexity
1. Add credential type: "HTTP Header Auth"
2. Name: "Perplexity"
3. Header Name: "Authorization"
4. Header Value: "Bearer YOUR_PERPLEXITY_API_KEY"

#### Tavily
1. Add credential type: "HTTP Header Auth"
2. Name: "Tavily"
3. Header Name: "Authorization"
4. Header Value: "Bearer YOUR_TAVILY_API_KEY"

#### Replicate
1. Add credential type: "HTTP Header Auth"
2. Name: "Replicate"
3. Header Name: "Authorization"
4. Header Value: "Token YOUR_REPLICATE_API_KEY"

#### SendGrid (Optional)
1. Add credential type: "HTTP Header Auth"
2. Name: "SendGrid"
3. Header Name: "Authorization"
4. Header Value: "Bearer YOUR_SENDGRID_API_KEY"

### 3. Connect Credentials to Nodes

After importing, connect credentials to nodes with red dots:

- **Main Claude Model** → Anthropic API
- **Research Model, Structure Model, Writer Model, etc.** → OpenAI API
- **Perplexity Research, Newsletter Trends** → Perplexity credentials
- **Tavily Newsletter Search** → Tavily credentials
- **Newsletter Image Generator** → Replicate credentials
- **Email to Substack** → SendGrid credentials (if using email method)

### 4. Configure Substack Settings

Edit these nodes with your Substack information:

**Email to Substack node:**
- Replace `your-publication@substack.com` with your actual Substack email
- Replace `your-email@domain.com` with your sending email

**Webhook Publisher node:**
- Replace `your-custom-webhook-url` with your webhook URL (if using)
- Replace `your-publication.substack.com` with your publication URL

## Usage

### 1. Start the Workflow
1. Click on the "Chat Trigger" node
2. Click "Test workflow" or "Execute workflow"
3. A chat interface will appear

### 2. Create Your First Newsletter
Enter a command like:
```
Create newsletter: The Rise of AI Automation in 2025
```

### 3. Review the Process
The system will:
1. Research newsletter-worthy content and trends
2. Create engaging subject line options
3. Structure content for email engagement
4. Write personal, conversational newsletter content
5. Generate an email-optimized header image
6. Format for Substack platform
7. Send to your Substack email as a draft

### 4. Available Commands
- **"Create newsletter: [topic]"** - Full workflow
- **"Draft newsletter: [topic]"** - Create draft only
- **"Research: [topic]"** - Research phase only
- **"Email newsletter: [topic]"** - Create and email to Substack

## Publishing Methods

### Method 1: Email to Substack (Recommended)
The workflow emails formatted content to your Substack email address, creating a draft in your Substack dashboard.

**Setup:**
1. Find your Substack publication email (Settings > Publishing > Email)
2. Update the "Email to Substack" node with this address
3. Configure SendGrid for reliable email delivery

### Method 2: Webhook Integration
For advanced users, set up browser automation to directly publish to Substack.

**Setup:**
1. Create webhook endpoint that handles Substack posting
2. Update "Webhook Publisher" node with your endpoint
3. Configure authentication and error handling

### Method 3: Manual Copy-Paste
The system provides formatted content for manual publishing.

**Process:**
1. System generates complete newsletter content
2. Copy formatted text from workflow output
3. Paste into Substack editor manually

## Customization

### Newsletter Writing Style
Edit the "Substack Writer Agent" prompt to modify:
- Personal voice and tone
- Story-telling approach
- Content length and sections
- Engagement techniques
- Call-to-action style

### Research Focus
Modify the "Newsletter Research Agent" to:
- Target specific industries or niches
- Include trending topics analysis
- Focus on subscriber interests
- Add competitive intelligence

### Email Optimization
Adjust the "Newsletter Structure Agent" for:
- Different subject line styles
- Mobile email formatting
- Engagement optimization
- Retention strategies

### Visual Style
Update the "Newsletter Visual Agent" for:
- Brand-consistent imagery
- Different visual themes
- Email-safe image formats
- Alternative design styles

## Newsletter Best Practices

### Content Structure
- **Personal Opening** (150-200 words) - Hook with story or insight
- **Main Insights** (3 sections, 300-400 words each)
- **Personal Reflection** (100-150 words)
- **Reader Engagement** (Question or poll)
- **Next Week Preview** (50-100 words)

### Email Optimization
- **Subject Lines**: Curiosity-driven, personal, value-focused
- **Length**: 1200-2000 words (6-10 minute read)
- **Format**: Short paragraphs, strategic bold text
- **Mobile**: Optimized for mobile email reading
- **CTAs**: Clear engagement and subscription retention

### Engagement Strategies
- Ask questions throughout content
- Share personal stories and opinions
- Include surprising data or insights
- Provide actionable takeaways
- Encourage replies and discussion

## Troubleshooting

### Common Issues

**Red dots on nodes:**
- Missing API credentials - complete setup steps

**Research fails:**
- Check Perplexity and Tavily API keys
- Verify rate limits and credits
- Confirm internet connectivity

**Image generation problems:**
- Verify Replicate API key and credits
- Check if prompt meets content guidelines
- Try simpler image descriptions

**Email delivery fails:**
- Confirm SendGrid API key and verification
- Check sending domain authentication
- Verify recipient email address

**Substack integration issues:**
- Confirm Substack email address is correct
- Check Substack account permissions
- Verify content format compatibility

### Performance Optimization

**Reduce Costs:**
- Use GPT-3.5-turbo for some agents
- Decrease research depth
- Skip image generation for drafts

**Improve Quality:**
- Add manual review steps
- Include fact-checking processes
- Implement feedback loops

**Enhance Engagement:**
- A/B test subject lines
- Track subscriber feedback
- Optimize send timing

## Cost Analysis

Typical cost per newsletter (1500-2000 words):

| Component | Cost Range |
|-----------|------------|
| Claude Sonnet 4 (orchestration) | $0.20-0.30 |
| GPT-4.1 Mini (agents) | $0.15-0.25 |
| Perplexity research | $0.15-0.25 |
| Tavily research | $0.05-0.10 |
| Replicate image | $0.15-0.25 |
| SendGrid email | $0.01-0.05 |
| **Total** | **$0.71-1.20** |

## Advanced Features

### Subscriber Segmentation
Customize content based on subscriber segments:
1. Add subscriber data inputs
2. Modify content based on interests
3. Personalize subject lines and content

### A/B Testing
Test different approaches:
1. Generate multiple subject line options
2. Create content variations
3. Track performance metrics

### Analytics Integration
Monitor newsletter performance:
1. Add webhook to analytics platform
2. Track open rates and engagement
3. Store content performance data

## Support

For issues or questions:
1. Check the troubleshooting section above
2. Review Substack documentation
3. Open an issue in this repository
4. Contact via LinkedIn: [@rawalrahul](https://linkedin.com/in/rawalrahul)

## License

This workflow is released under the MIT License. See the main repository LICENSE file for details.