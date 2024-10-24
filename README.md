# Technical assessment 

## Overview
This is a guide to do a technical assessment for a technology product. It covers various areas that should be looked at and key indicators to derive a sense of overall health

## Code conventions
### Mental model
Conventions on a large team are powerful. They lend familiarity and allow team to work in synchronization while reducing communications overhead. Even if code is not written in an ideal structure, if conventions are followed diligently, code will be predictable and easy to navigate. In legacy code base, strong conventions can lend ease of maintainance and onboarding. 

### Benefits (_of a strong convention system_)
- [ ] Readability
- [ ] Maintainability
- [ ] Consistency

### Anti patterns
- [ ] **Magic strings** - String embedded into the code directly. These are anti-pattern because they reduce reusability and require duplicate code changes for any string change. Ideally should be externalized, if not into a config then into a variable. For i18n it is ideal to extract into config files that can be translated and substituted
- [ ] **Hard-coded error messages** - Error messages should be treated as strings, and should be either maintained with constants at minimum or be externalized as strings
- [ ] **Unused imports** - Unused imports increase code clutter and while are often optimized by compilers at compile time, they can have a performance impact during compile time if not at runtime
- [ ] **Unformatted code** - Inconsistently formatted code is harder to read

### Best practices
- [ ] **Code linters** - Embed tooling in CI pipeline to identify linting errors and fail the build when errors exist
- [ ] **Pre-commit hook for code formatting** - Have IDE based automatic code formatting or enable a pre-commit hook to ensure code is formatted and imports are optimized
- [ ] **Configuration management** - Manage configuration consistently across application. Differentiate between secrets and configurations. Allow configurations to be overridden by different environment/profiles. Use established formats like YAML, properties etc. for managing config. Properties should be separated from the code and ideally should be possible to hot reload properties in a running application. 
- [ ] **Naming** - Name for classes should be Nouns or noun phrases (_Customer, UserProfile etc._) and should be concrete instead of being generic (_Data, Object_). Properties of a class should be noun or adjectives (_age, isActive etc_). Methods should be verb or verb phrases (_sendEmail, loadProfile etc._) and should be concrete instead of being generic (_process, execute etc._). Configuration properties should be named appropriately as well (_timeDelayInMillis is better than timeDelay_). Use domain terminology in naming and relationships between objects.
- [ ] **Document coding conventions** - Type of casing for the code, naming conventions for configuration properties, code elements, rest endpoints, database tables & columns, queue names, cloud components, etc. Outline a predictable code layout and structure. Adopt language idioms and document them. Avoid redudant code comments. If possible generate and review comments for code using coding assistants and keep them updated


## REST/WEB API Specifications
Web APIs are a dominant integration point for applications. Design is difficult in future and require complex manouvering like versioning, backward-compatibility when active consumers exist. It is crucial to have a future proofing view on WEB specifications to ensure that contracts offer as much flexibility as possible and remain malleable to defer complexity of versioning and wider structural changes. 

### Benefits
- [ ] Integrations / Interoperability
- [ ] Modularity (_composing via integrations_)

### Anti patterns
- [ ] Usage of incorrect HTTP verbs or mutating state on GET verb or executing updates with POST
- [ ] Inconsistent response formats
- [ ] Non standard error codes
- [ ] Ignoring HTTP methods/verbs
- [ ] Usage of verbs in resource names
- [ ] Convoluted versioning schemes

### Best practices
- [ ] **Structured content, metadata & error** - API contract with placeholders for content, metadata and error messages that remains consistent across API
- [ ] **HATEOAS Level 2** - Usage of atleast Level II HATEOAS standards in REST APIs (Resources, Methods, Status code, Query params and Headers)
- [ ] **Versioning** - If there is a need for backward compatibility or versioning in API, then url versioning or header based versioning should be in place
- [ ] **Error handling** - Errors should be handled with messages, code and HTTP status codes to provide a consistent experience and right status codes should be mapped. 5xx vs 4xx for different error categories
- [ ] **Security** - Consistent authentication and authorization mechanisms should be followed. Preferably something along the lines of JWT Tokens using OAuth 2.0. SSL termination should happen at the entry point
- [ ] **Documentation** - Live documentation for the API using tools like swagger to have a functioning API playground as well as updated documentation that is auto generated with changes to the API
- [ ] **Etags/Caching** - Response caching should be enabled using ETags
- [ ] **Pagination / Metadata** - Response should include metadata on total number of elements, total number of pages, elements per page and current page number. Additional good to have would be navigation elements for the next and previous pages in the response 


## Domain model
### Ideal


### Checklist


### Key Indicators





