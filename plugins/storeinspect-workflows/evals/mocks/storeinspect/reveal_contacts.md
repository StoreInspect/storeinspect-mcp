---
expect:
  contact_ids: array
  confirm_spend_credits: true
---

{
  "object": "contact_reveal_result",
  "credits": {
    "spent": 1,
    "remaining": 4
  },
  "data": [
    {
      "id": "ct_fixture_cedar_founder",
      "object": "contact",
      "full_name": "Alex Rowan",
      "first_name": "Alex",
      "last_name": "Rowan",
      "title": "Founder",
      "role": "founder",
      "seniority": "executive",
      "linkedin_url": null,
      "emails": [
        {
          "email": "alex@cedar-fashion.example",
          "status": "verified",
          "type": "professional",
          "is_primary": true
        }
      ],
      "phones": [],
      "store": {
        "id": "st_fixture_cedar",
        "domain": "cedar-fashion.example",
        "name": "Cedar Fashion"
      },
      "revealed_at": "2026-10-18T09:00:00Z",
      "reveal_status": "newly_revealed",
      "charged": true
    }
  ]
}
