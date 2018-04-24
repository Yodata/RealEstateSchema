# Organization

An organization such as a Broker or Office that has members, which can be Agents, Employees or another Organization.

## Organization Events

### Example 1: An Agent record was created or updated.

```json
{
  "id": "https://example.com/inbox/d9939ab6b3a54c9e991443ee629bd912",
  "type": "Notification",
  "timestamp": 1524589743265,
  "object": {
    "type": "AddAction",
    "Object": {
      "type": "Person",
      "id": "https://alice.example.com/profile/card#me",
      "identifier": [
        {
          "type": "PropertyValue",
          "name": "externalAgentId",
          "value": "alice"
        }
      ],
      "givenName": "Alice",
      "familyName": "Agent",
      "name": "Alice Agent",
      "email": ["alice@example.com"],
      "status": "Active",
      "faxNumber": "(843) 338-8119",
      "telephone": "(843) 478-8598",
      "memberOf": [
        {
          "id": "https://office_123.example.com/profile/card#me",
          "type": "Organization"
        }
      ],
      "hasRole": [],
      "geoJSON": {
        "coordinates": [0, 0],
        "type": "Point"
      },
        "photo": [],
        "openingHoursSpecification": [],
        "logo": []
      },
      "birthPlace": {
        "geoJSON": {
          "coordinates": [0, 0],
          "type": "Point"
        },
        "photo": ["http://alice.example.com/profile/image.jpg"],
        "openingHoursSpecification": [],
        "logo": []
      },
      "workLocation": {
        "telephone": "(843) 478-8598",
        "hoursAvailable": [],
        "contactOption": []
      },
      "availableLanguage": [
          "English",
          "Spanish"
      ]
    }
  }
}
```
