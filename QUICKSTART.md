# Quick Start: Publishing Your Credit-Based Pricing Skill

## Goal
Get this skill published to GitHub so prospects and customers can install it in Claude Code.

## What You're Getting
This package contains everything needed to distribute a Claude Code skill:
- ✅ SKILL.md with complete credit-based pricing guidance
- ✅ plugin.json with proper configuration
- ✅ README with installation instructions
- ✅ LICENSE (MIT)
- ✅ Proper directory structure

## 5-Minute Deployment

### Step 1: Create a GitHub Repository

```bash
# Navigate to the plugin directory
cd /path/to/credit-pricing-plugin

# Initialize git
git init

# Add all files
git add .

# Make initial commit
git commit -m "Initial release: Credit-based pricing launch skill v1.0.0"
```

### Step 2: Push to GitHub

Option A - Create via GitHub UI:
1. Go to https://github.com/schematic-hq (or your org)
2. Click "New repository"
3. Name: `claude-credit-pricing-skill`
4. Public or Private (your choice)
5. Don't initialize with README (you already have one)
6. Create repository

```bash
# Add remote (replace with your actual URL)
git remote add origin [email protected]:schematic-hq/claude-credit-pricing-skill.git

# Push
git branch -M main
git push -u origin main
```

Option B - Create via GitHub CLI:
```bash
gh repo create schematic-hq/claude-credit-pricing-skill --public --source=. --remote=origin --push
```

### Step 3: Test Installation

Test that the skill installs correctly:

```bash
# In Claude Code, add your marketplace
/plugin marketplace add github:schematic-hq/claude-credit-pricing-skill

# Install the plugin
/plugin install credit-pricing-launch@schematic-hq

# Restart Claude Code

# Test the skill
/credit-pricing-launch
```

### Step 4: Share with Prospects/Customers

Now you can share installation instructions:

**For Slack/Email:**
```
We've built a Claude Code skill that guides technical teams through 
launching credit-based pricing. 

Install it:
/plugin marketplace add github:schematic-hq/claude-credit-pricing-skill
/plugin install credit-pricing-launch@schematic-hq

Then restart Claude Code and type /credit-pricing-launch
```

**For LinkedIn:**
```
We just open-sourced a Claude skill for launching credit-based pricing 
in AI/SaaS products 🚀

Covers strategic validation → technical architecture → edge cases.

Install: github:schematic-hq/claude-credit-pricing-skill

Built for VP Eng, Staff Engineers, and PMs navigating consumption pricing.
```

## Testing Before You Share

### Test Locally First

Before pushing to GitHub, test the skill works:

```bash
# From the plugin directory
claude --plugin-dir /path/to/credit-pricing-plugin

# Try these test queries:
"How should I think about credit-based pricing?"
"Help me implement credit burndown"
"What are the edge cases with credit systems?"
```

Claude should automatically invoke the skill and provide guidance from SKILL.md.

### Verify Structure

```bash
# Check your directory structure matches:
tree -L 3

# Should output:
# credit-pricing-plugin/
# ├── .claude-plugin/
# │   └── plugin.json
# ├── skills/
# │   └── credit-pricing-launch/
# │       └── SKILL.md
# ├── .gitignore
# ├── LICENSE
# ├── README.md
# └── QUICKSTART.md
```

## Updating the Skill

When you want to make changes:

1. Edit `skills/credit-pricing-launch/SKILL.md`
2. Update version in `.claude-plugin/plugin.json` (e.g., `1.0.0` → `1.1.0`)
3. Commit and push:
   ```bash
   git add .
   git commit -m "Update: Added section on XYZ"
   git push
   ```
4. (Optional) Create a GitHub release for version tracking

Users will get updates when they run:
```
/plugin marketplace update
/plugin update credit-pricing-launch@schematic-hq
```

## Making It Private

If you want this skill to be private (only accessible to specific people):

1. Make the GitHub repo private
2. Share installation instructions only with specific people
3. They'll need GitHub access to the repo to install

Private repositories work the same way with Claude Code plugins.

## Next Steps

**For Sales:** Add to your sales deck, include in technical discovery calls

**For Marketing:** 
- Blog: "We built a Claude skill for credit pricing" 
- LinkedIn post with installation instructions
- Developer newsletter

**For Customer Success:** Reference in onboarding docs, share when customers ask about credit implementation

## Troubleshooting

**Skill not loading:**
- Verify directory structure matches exactly
- Check that SKILL.md has proper frontmatter (--- delimiters)
- Restart Claude Code after installation

**Plugin install fails:**
- Verify repository is public (or user has access)
- Check GitHub URL is correct
- Try: `/plugin marketplace update` first

**Claude doesn't invoke skill automatically:**
- Check the `description` field in SKILL.md frontmatter
- Try invoking manually first: `/credit-pricing-launch`
- Verify skill is enabled: `/plugin list`

## Questions?

If you hit issues, check:
- Claude Code docs: https://docs.claude.com/en/docs/claude-code/plugins
- Or reach out to your Anthropic contact
