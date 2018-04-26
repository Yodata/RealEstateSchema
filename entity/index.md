# Entity Data Model

## Base Types (schema.org)

## Thing

Any entity that can be accessed or unambiguously identified by URL.

## Person

A person (alive, dead, undead, or fictional).

## Place

Entities that have a somewhat fixed, physical extension.

## Organization

An Office, Company, or Team that has members.

## Event

An event happening at a certain time and location, such as a concert, lecture, or festival. Ticketing information may be added via the offers property. Repeated events may be structured as separate Event objects.

## Action

An action performed by a direct agent and indirect participants upon a direct object. Optionally happens at a location with the help of an inanimate instrument. The execution of the action may produce a result. Specific action sub-type documentation specifies the exact expectation of each argument/role.

## Role

Represents additional information about a relationship or property. For example a Role can be used to say that a 'member' role linking some SportsTeam to a player occurred during a particular time period. Or that a Person's 'actor' role in a Movie was for some particular characterName. Such properties can be attached to a Role entity, which is then associated with the main entities using ordinary properties like 'member' or 'actor'.

## Real Estate Types

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
