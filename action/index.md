# Real Estate Schema: Actions

Actions, based on [schema.org/Action](http://schema.org/Action) enable real-time application integration.

### Example
```html
<!--  John listened to Pink with Steve at Anna's apartment on his iPod. -->
<script type="application/ld+json">
{
  "@context": "http://schema.org",
  "@type": "ListenAction",
  "agent": {
    "@type": "Person",
    "name": "John"
  },
  "object": {
    "@type": "MusicGroup",
    "name": "Pink!"
  },
  "participant": {
    "@type": "Person",
    "name": "Steve"
  },
  "location": {
    "@type": "Residence",
    "name": "Ann's apartment"
  },
  "instrument": {
    "@type": "Product",
    "name": "iPod"
  }
}
</script>
```

## Real Estate Actions for Software Integration

# Real Estate Website

Actions produced by a RealEstateWebsite.

Common Properties of Website Actions
Properties common in actions generated by real estate websites include:

| PROPERTY | TYPE   | DESCRIPTION                                                                                                   |
| -------- | ------ | ------------------------------------------------------------------------------------------------------------- |
| agent    | Person | The user visiting the website                                                                                 |
| object   | Thing  | the primary subject of the integration, for example a listing viewed, a search saved, a question being asked. |

## Website Actions

| USER ACTIVITY                                   | PRODUCES ACTION   |
| ----------------------------------------------- | ----------------- |
| views any page on the website                   | ViewAction        |
| registers as a user on an agent website or blog | RegisterAction    |
| unregisters or deletes account                  | UnregisterAction  |
| executes a property search                      | SearchAction      |
| likes, favorites or stars a property listing    | LikeAction        |
| dislikes a property                             | IgnoreAction      |
| saves a search                                  | SubscribeAction   |
| deletes a saved search                          | UnsubscribeAction |
| updates search parameters of a saved search     | UpdateAction      |
| asks a question                                 | AskAction         |
| sends a listing                                 | SendAction        |

## Website Action Examples

```YAML
    // Examples shown in YAML, but must be converted to JSON for actual use.

    // These actions reference the real estate context
    // published via yodata.io schema collaboration platform.
    @context: 'https://yodata.io/yodata/realestate/context'

    // Betty visits the real estate website of AndyAgent
    @type: ViewAction
    agent: Betty Browser
    instrument: 'http://andyagent.com/'

    // Betty registers or creates an account on Andy's website
    @type: RegisterAction
    instrument: http://andyagent.com/signup
    agent:
      // @id not required. Can be the URL of the users homepage
      @id: http://andyagent.com/user/123
      @type: Person
      name: Betty Buyer
      email: betty@example.com

    // Betty runs a property search
    @type: SearchAction
    agent:
      @type: Person
      name: Betty Buyer
      email: betty@example.com
    object:
      // Search Data Structure WIP, contact dave@yodata.io
      @type: RealEsatePropertySearch

    // Betty views a listing
    @type: ViewAction
    agent:
      @type: Person
      name: Betty Buyer
      email: betty@example.com
    instrument: http://andyagent.com/
    object: http://andyagent.com/search/123456 // full listing detail not required
                                               // for a simple view.

    // Betty sends a property listing to someone
    @type: SendAction
    agent:
      @type: Person
      name: Betty Buyer
      email: betty@example.com
    recipient:
      @type: Person
      email: bruce@example.com
    instrument: http://andyagent.com
    object:
      @type: RealEstateListing
      @id: http://andyagent.com/search/123456
      address: 123 Main Street
      // best practice: include full property details here

    // Betty saves a search
    @type: SubscribeAction
    agent:
      @type: Person
      name: Betty Buyer
      email: betty@example.com
    instrument: http://andyagent.com
    object:
      // Data structure for search is WIP
      @type: RealEstatePropertySearch
      @id: http://andyagent.com/search?savedSearchID=...
```

---

# Real Estate Organization Events

General administrative events related to a real estate organization.

# Real Estate Listing Events

WIP

# Real Estate Transaction Events

WIP