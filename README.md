# Real Estate Integration Schema

Standard data model for integrating software and services in the real estate industry based on schema.org, RESO, linked-data-platform...

## About the Project

We aim to accelerate innovation in the real estate industry thorough open source and collaboration with like minded individuals and companies.

The project is 100% community driven. Feedback, suggestions and contributions are very welcome.

Please contact dave@yodata.io if you'd like to get invovled or get some help implementing the existing event model.

## Technical Foundatation & Inspiration

* http://schema.org - base context and Actions vocabulary
* RESO Data Dictionary - real estate listing data

# Classes

## Thing

Any entity that can be accessed or unambiguously identified by URL.

## Person

A person (alive, dead, undead, or fictional).

## Place

Entities that have a somewhat fixed, physical extension.

## Organization(/entity/Organization/index.md)

A Company, Office or Team that has members.

## Event

An event happening at a certain time and location, such as a concert, lecture, or festival. Ticketing information may be added via the offers property. Repeated events may be structured as separate Event objects.

## Action

An action performed by a direct agent and indirect participants upon a direct object. Optionally happens at a location with the help of an inanimate instrument. The execution of the action may produce a result. Specific action sub-type documentation specifies the exact expectation of each argument/role.

## Role

Represents additional information about a relationship or property. For example a Role can be used to say that a 'member' role linking some SportsTeam to a player occurred during a particular time period. Or that a Person's 'actor' role in a Movie was for some particular characterName. Such properties can be attached to a Role entity, which is then associated with the main entities using ordinary properties like 'member' or 'actor'.

# Real Estate Types

These types extend schema.org for more clarity and/or to simply mapping of data structures commonly used within real estate industry applications including CRM, Real Estate Websites, Transaction Management, Marketing and Back Office Accounting systems.

## RealEstateAgent

In schema.org parlance, RealEstateAgent extends LocalBusiness and Organization, and therefore RealEstateAgent is used to represent solo agents, teams, and offices.

Note: For greater clarity, we use RealEstateOrganization to represent Offices, Brokers and Franchisors.

## RealEstateOrganization

An organization who’s members are RealEstateAgents, for example an Office, Broker or Franchisor.

## RealEstateListing

Equivalent to RESO:Listing.

## RealEstateWebsite

Extends http://schema.org/Website. RealEstateWebsites produce website actions (events).

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