---
expect:
  filters.countries: array
  filters.apps.none: array
  limit: 10
---

{
  "object": "list",
  "data": [
    {
      "id": "st_fixture_cedar",
      "object": "store",
      "domain": "cedar-fashion.example",
      "name": "Cedar Fashion",
      "category": "fashion",
      "country": "GB",
      "traffic_tier": "medium",
      "revenue_tier": null,
      "shopify_plus": false,
      "lead_fit_score": null,
      "store_created_at": null,
      "first_discovered_at": null,
      "technologies": {
        "apps": [],
        "pixels": [
          "meta"
        ],
        "theme": {
          "name": "Dawn",
          "type": "free"
        }
      },
      "contacts_summary": {
        "total": 1,
        "has_revealable_contacts": true,
        "verified_email_count": 1,
        "roles": [
          "founder"
        ]
      }
    }
  ],
  "has_more": false,
  "next_cursor": null
}
