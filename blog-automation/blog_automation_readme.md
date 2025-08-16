# Blog Automation - Medium Publishing Workflow

A sophisticated multi-agent AI system that automates the entire blog creation process from topic research to publication on Medium.

## Overview

This workflow creates complete, high-quality blog posts optimized for Medium in 3-5 minutes instead of 4-6 hours of manual work. The system uses specialized AI agents for research, writing, image generation, and publishing.

## Architecture

### Agent System
- **Advanced Research Agent** - Multi-source research using Perplexity + Tavily
- **SEO Title & Structure Agent** - Creates optimized titles and content structure
- **Medium Writer Agent** - Writes engaging, Medium-optimized content
- **Medium Visual Agent** - Generates professional hero images
- **Medium Format Agent** - Formats content for Medium platform
- **Medium Publishing Agent** - Handles direct publication to Medium

### Tech Stack
- **Orchestration**: n8n workflow automation
- **Main LLM**: Claude Sonnet 4 (orchestrator)
- **Supporting Models**: GPT-4.1 Mini (specialized agents)
- **Research**: Perplexity Pro + Tavily APIs
- **Images**: Replicate (Flux model)
- **Publishing**: Medium API

## Prerequisites

### Required API Keys

1. **Anthropic API** (Claude Sonnet 4)
   - Sign up at: https://console.anthropic.com/
   - Cost: ~$0.20-0.40 per article

2. **OpenAI API** (GPT-4.1 Mini)
   - Sign up at: https://platform.openai.com/
   - Cost: ~$0.10-0.20 per article

3. **Perplexity API**
   - Sign up at: https://docs.perplexity.ai/
   - Cost: ~$0.10-0.15 per article

4. **Tavily API**
   - Sign up at: https://tavily.com/
   - Cost: ~$0.05-0.10 per article

5. **Replicate API** (Image Generation)
   - Sign up at: https://replicate.com/
   - Cost: ~$0.10-0.20 per image

6. **Medium API** (Publishing)
   - Get token at: https://medium.com/me/settings/publishing
   - Free (Medium platform fees may apply)

### System Requirements
- n8n instance (self-hosted or cloud)
- Minimum 2GB RAM for workflow execution
- Stable internet connection

## Installation

### 1. Import Workflow
1. Download `blog-workflow.json` from this repository
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

#### Medium API
1. Add credential type: "HTTP Header Auth"
2. Name: "Medium"
3. Header Name: "Authorization"
4. Header Value: "Bearer YOUR_MEDIUM_INTEGRATION_TOKEN"

### 3. Connect Credentials to Nodes

After importing, you'll see red dots on certain nodes. Click each node and assign the appropriate credentials:

- **Main Claude Model** → Anthropic API
- **Research Model, Structure Model, Writer Model, etc.** → OpenAI API
- **Enhanced Perplexity** → Perplexity credentials
- **Enhanced Tavily** → Tavily credentials
- **Medium Image Generator** → Replicate credentials
- **Get Medium User, Publish to Medium** → Medium credentials

## Usage

### 1. Start the Workflow
1. Click on the "Chat Trigger" node
2. Click "Test workflow" or "Execute workflow"
3. A chat interface will appear

### 2. Create Your First Blog Post
Enter a command like:
```
Write and publish to Medium: The Future of AI in Healthcare
```

### 3. Review the Process
The system will:
1. Research the topic comprehensively
2. Create SEO-optimized structure and titles
3. Write engaging, Medium-optimized content
4. Generate a professional hero image
5. Format everything for Medium
6. Publish directly to your Medium account

### 4. Publishing Options
- **"Write and publish to Medium: [topic]"** - Full automation
- **"Save as draft: [topic]"** - Create but don't publish
- **"Research only: [topic]"** - Stop before writing

## Customization

### Modify Writing Style
Edit the "Medium Writer Agent" prompt to change:
- Tone (professional, casual, technical)
- Length (short-form, long-form)
- Target audience
- Personal voice elements

### Adjust Research Focus
Modify the "Advanced Research Agent" to:
- Include specific sources
- Focus on certain types of data
- Change research depth
- Add industry-specific queries

### Change Image Style
Update the "Medium Visual Agent" prompts for:
- Different visual styles
- Brand-specific elements
- Custom aspect ratios
- Alternative image sources

## Troubleshooting

### Common Issues

**Red dots on nodes after import:**
- Missing API credentials - follow setup steps above

**"API key invalid" errors:**
- Check API key format and permissions
- Ensure sufficient API credits

**Workflow fails at research step:**
- Verify Perplexity and Tavily credentials
- Check internet connectivity
- Confirm API rate limits

**Image generation fails:**
- Check Replicate API key and credits
- Verify image prompt is appropriate
- Try simpler image descriptions

**Medium publishing fails:**
- Confirm Medium integration token is valid
- Check Medium account permissions
- Verify article format meets Medium requirements

### Performance Optimization

**Reduce Costs:**
- Use GPT-3.5-turbo instead of GPT-4.1 for some agents
- Decrease research depth parameters
- Skip image generation for drafts

**Improve Speed:**
- Use smaller context windows
- Enable parallel processing where possible
- Cache research results for similar topics

**Enhance Quality:**
- Increase temperature for more creative writing
- Add manual approval steps before publishing
- Include fact-checking verification steps

## Cost Analysis

Typical cost per 2000-word blog post:

| Component | Cost Range |
|-----------|------------|
| Claude Sonnet 4 (orchestration) | $0.15-0.25 |
| GPT-4.1 Mini (agents) | $0.10-0.20 |
| Perplexity research | $0.08-0.12 |
| Tavily research | $0.03-0.07 |
| Replicate image | $0.10-0.20 |
| Medium API | Free |
| **Total** | **$0.46-0.84** |

## Advanced Configuration

### Batch Processing
Modify the workflow to process multiple topics:
1. Add a "Split In Batches" node
2. Create topic queue management
3. Add rate limiting for API calls

### Quality Control
Add approval steps:
1. Insert "Human" approval nodes
2. Add content review webhooks
3. Implement feedback loops

### Analytics Integration
Track performance:
1. Add webhook to analytics platform
2. Store article metadata
3. Monitor engagement metrics

## Support

For issues or questions:
1. Check the troubleshooting section above
2. Review n8n documentation
3. Open an issue in this repository
4. Contact via LinkedIn: [@rawalrahul](https://linkedin.com/in/rawalrahul)

## License

This workflow is released under the MIT License. See the main repository LICENSE file for details.