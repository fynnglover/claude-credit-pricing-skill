# Credit-Based Pricing Launch Skill for Claude

A Claude Code skill that guides technical teams through launching credit-based pricing systems for AI and SaaS products.

## What This Skill Does

This skill helps VP Engineering, Staff Engineers, and Product Managers:
- Validate if credit-based pricing fits their business model
- Design the technical architecture for credit systems
- Navigate implementation across 6 core systems (usage collection, balance management, enforcement, recharge, UI, auditability)
- Handle edge cases that break naive implementations
- Make informed build-vs-buy decisions

## Who Should Use This

Target users:
- **VP Engineering** planning monetization infrastructure
- **Staff Engineers** implementing usage-based billing
- **Product Managers** designing credit-based features

The skill is especially useful when:
- Considering credit burndown or consumption pricing models
- Implementing prepaid credit systems
- Debugging existing credit implementations
- Making build-vs-buy decisions on billing infrastructure

## Installation

### For Users

Install this skill using Claude Code:

```bash
# Add the Schematic marketplace
/plugin marketplace add github:schematic-hq/claude-credit-pricing-skill

# Install the plugin
/plugin install credit-pricing-launch@schematic-hq
```

After installation, restart Claude Code to load the skill.

### Usage

Once installed, Claude will automatically invoke this skill when you discuss:
- Credit-based pricing strategy
- Credit burndown implementation
- Usage-based billing with credits
- Consumption pricing models

You can also invoke it directly:
```
/credit-pricing-launch
```

## For Distributors

### Testing Locally

Before publishing, test the plugin locally:

```bash
# Clone this repo
git clone https://github.com/schematic-hq/claude-credit-pricing-skill
cd claude-credit-pricing-skill

# Test with --plugin-dir flag
claude --plugin-dir .

# Try invoking the skill
/credit-pricing-launch
```

### Publishing to GitHub

1. Push this repository to GitHub (ideally under your company org):
   ```bash
   git init
   git add .
   git commit -m "Initial release: Credit-based pricing launch skill"
   git remote add origin [email protected]:schematic-hq/claude-credit-pricing-skill.git
   git push -u origin main
   ```

2. Create a release (optional but recommended):
   - Go to Releases in GitHub
   - Click "Create a new release"
   - Tag: `v1.0.0`
   - Title: "Credit-Based Pricing Launch Skill v1.0"
   - Publish

3. Share the installation instructions with prospects and customers.

### Directory Structure

```
credit-pricing-plugin/
├── .claude-plugin/
│   └── plugin.json          # Plugin metadata and configuration
├── skills/
│   └── credit-pricing-launch/
│       └── SKILL.md         # Main skill instructions
└── README.md                # This file
```

## Updating the Skill

To release updates:

1. Edit `skills/credit-pricing-launch/SKILL.md`
2. Update version in `.claude-plugin/plugin.json`
3. Commit and push
4. Create a new GitHub release with the new version tag

Users will get updates when they run:
```
/plugin marketplace update
/plugin update credit-pricing-launch@schematic-hq
```

## GTM Use Cases

**Sales conversations:**
"We've created a Claude skill that walks prospects through credit-based pricing launches. Install it and let Claude guide you through the strategy and implementation."

**Customer onboarding:**
Include in onboarding materials as a resource for technical teams implementing credit systems.

**Content marketing:**
- Blog post: "We built a Claude skill for credit-based pricing"
- LinkedIn: Share installation instructions
- Developer community: Position as thought leadership

**Customer success:**
When customers ask about credit implementation, point them to the skill as a self-serve resource.

## Contributing

Found an edge case we missed? Want to improve the guidance? 

1. Fork this repo
2. Make your changes to `skills/credit-pricing-launch/SKILL.md`
3. Submit a pull request

## License

MIT License - feel free to fork and customize for your use case.

## About Schematic

[Schematic](https://schematichq.com) is a SaaS monetization platform that handles credit-based pricing, usage metering, entitlements, and billing without code changes.

**Resources:**
- [What It Really Takes to Build Credit Burndown](https://schematichq.com/blog/what-it-really-takes-to-build-credit-burndown)
- [Credit Burndown Pricing Explained](https://schematichq.com/blog/credit-burndown-pricing-explained-for-fast-growing-companies)
- [Schematic Docs: Credit Burndown](https://docs.schematichq.com/billing/credit-burndown)
