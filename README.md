# Google Maps Lead Intelligence & Contact Enrichment

Turn any Google Maps search into a complete, ready to use outreach list. One click gets you business contacts, validated emails, social profiles, and lead scores.

Built for lead gen agencies, local SEO companies, appointment setting services, and cold email teams who need qualified local business leads fast.

## What You Get

Enter a search like "dentists in Miami FL" and receive a fully enriched lead package:

- **Business data** from Google Maps (name, address, phone, rating, reviews, hours, category)
- **Contact enrichment** (emails, social profiles, technologies, company description)
- **Email validation** (every email checked for deliverability)
- **Lead scoring** (0 to 100 score based on data quality and business signals)
- **Ranked list** sorted by lead quality, ready for outreach

## Why This Exists

Your team currently spends 3 to 4 hours per search doing this manually:

1. Search Google Maps and copy business info into a spreadsheet
2. Visit each website to find email addresses
3. Check social profiles one by one
4. Validate emails through a separate tool
5. Decide which leads to contact first

This actor does all five steps in one run. The entire pipeline runs automatically while you focus on closing deals.

## Price Comparison

| Method | Cost per search | Time |
|--------|----------------|------|
| Manual research | $200 (4 hours at $50/hr) | 4 hours |
| Apollo.io | $99/month for 5K credits | Still manual work |
| Hiring a VA | $500/month minimum | Training required |
| **This actor** | **$39 per search** | **Fully automatic** |

## How It Works

```
Search query  -->  Google Maps scrape  -->  Website enrichment  -->  Email validation  -->  Scored lead list
                   (20+ businesses)        (emails, socials)       (deliverability)      (ranked 0 to 100)
```

1. Scrapes Google Maps for your search query using a real browser
2. Enriches each business website to find emails, social profiles, and tech stack
3. Validates every discovered email address
4. Scores and ranks each lead based on data completeness and business quality

## Input

| Field | Type | Default | Description |
|-------|------|---------|-------------|
| searchQuery | string | required | What to search on Google Maps. Include location. Example: "plumbers in Dallas TX" |
| maxResults | integer | 20 | Maximum businesses to scrape (1 to 100) |
| enrichWebsites | boolean | true | Enrich each business with website contact data |
| validateEmails | boolean | true | Validate all discovered emails |
| minRating | number | 0 | Only include businesses with this rating or higher |

### Example Input

```json
{
    "searchQuery": "dentists in Miami FL",
    "maxResults": 20,
    "enrichWebsites": true,
    "validateEmails": true,
    "minRating": 3.0
}
```

## Output

Each lead in the output contains:

```json
{
    "rank": 1,
    "leadScore": 92,
    "businessName": "Smile Design Dental",
    "category": "Dentist",
    "address": "123 Main St, Miami, FL 33101",
    "phone": "+1-305-555-0123",
    "website": "https://smiledesigndental.com",
    "rating": 4.8,
    "reviewCount": 234,
    "hours": "Mon to Fri 8AM to 5PM",
    "googleMapsUrl": "https://maps.google.com/...",
    "emails": [
        {
            "email": "info@smiledesigndental.com",
            "valid": true,
            "score": 0.9
        }
    ],
    "socialProfiles": {
        "facebook": "https://facebook.com/smiledesigndental",
        "instagram": "https://instagram.com/smiledesigndental"
    },
    "enrichment": {
        "industry": "Healthcare",
        "technologies": ["WordPress", "Mailchimp"],
        "description": "Full service dental practice in Miami"
    },
    "enrichedAt": "2026-04-12T10:30:00.000Z"
}
```

## Lead Scoring

Every lead gets a score from 0 to 100. Higher scores mean more complete data and stronger business signals:

| Signal | Points |
|--------|--------|
| Has phone number | +15 |
| Has website | +15 |
| Has email address | +20 |
| Email validated as deliverable | +10 |
| Rating 4.0 or higher | +15 |
| Rating 4.5 or higher | +5 bonus |
| More than 50 reviews | +10 |
| More than 100 reviews | +5 bonus |
| Has social profiles | +5 |

A score of 80+ means the lead has strong contact data and good business reputation. Start your outreach there.

## Use Cases

**Lead gen agencies**: Search for any local business type in any city. Get a complete outreach list in minutes instead of hours. Run multiple searches per day to fill your pipeline.

**Local SEO companies**: Find businesses in your target market that need SEO services. The tech stack data tells you what platform they use so you can tailor your pitch.

**Appointment setting services**: Get phone numbers and emails for local businesses. The lead score tells you which ones are worth calling first.

**Cold email teams**: Get validated email addresses ready for your email sequences. No more bounced emails killing your sender reputation.

**Sales teams**: Research a local market before entering it. Know every competitor, their ratings, and how to reach them.

## Tips for Best Results

1. **Be specific with location**: "plumbers in Dallas TX" works better than just "plumbers"
2. **Use minRating filter**: Set minRating to 3.5 or 4.0 to focus on established businesses
3. **Start with 20 results**: The default of 20 gives you a solid list. Increase to 50 or 100 for larger markets
4. **Export as CSV**: Download results from the Dataset tab for easy import into your CRM or email tool

## Integrations

Export your leads directly to:

- Google Sheets (via Apify integration)
- Zapier (trigger on new dataset)
- Make/Integromat
- Any CRM via webhook
- CSV/JSON/Excel download

## Support

Questions or custom requirements? Reach out through the Apify Store or open an issue on GitHub.
