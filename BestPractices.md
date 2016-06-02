# Best Practices
Proposed best practices (coding conventions, git, etc) for MedBook

## Deploys

  * Follow the git branching model proposed here: http://nvie.com/posts/a-successful-git-branching-model/
  * Before pushing a deploy to Develop, perform a code review with one other person, with an eye towards security. 
  In particular, check that all changed Publish and Meteor Methods maintain correct security.
  
## Code Style

### Naming Conventions
(From https://github.com/UCSC-MedBook/primary-collections/blob/master/README.md )
#### Collections
Mongo collection names should be snake case. Meteor collection names should be camel case and begin with a capital letter.

```js
import { Mongo } from 'meteor/mongo';

CollectionName = new Mongo.Collection("collection_name");
```

Attribute names should be snake case and should be descriptive. When representing the same data type across collections, 
the same attribute name should be used.




