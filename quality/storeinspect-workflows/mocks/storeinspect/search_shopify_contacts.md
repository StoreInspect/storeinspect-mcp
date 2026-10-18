---
expect:
  store.domains: array
  max_contacts_per_store: 1
---

{
  "object": "list",
  "data": [
    {
      "id": "ct_fixture_cedar_founder",
      "object": "contact_preview",
      "first_name": "Alex",
      "last_name_obfuscated": "R***",
      "role": "founder",
      "seniority": "executive",
      "title": "Founder",
      "has_verified_email": true,
      "has_phone": false,
      "has_linkedin": true,
      "revealed": false,
      "store": {
        "id": "st_fixture_cedar",
        "domain": "cedar-fashion.example",
        "name": "Cedar Fashion"
      }
    }
  ],
  "has_more": false,
  "next_cursor": null
}
