# Style Guide conventions

This guide is basically a fork of airbnb's guide style https://github.com/airbnb/javascript. If a policy does not exist or has not been implemented here, please fallback to it.

> There are only two hard things in Computer Science: cache invalidation and naming things.
> -- Phil Karlton

* Commits, Pull requests and branches
* Classes
* Functions
* Variables
* Files & Folders
* JSON & Objects

### No semicolons.
We are happy about it. [It's][1] [fine.][2] [Really!][3]

[1]: http://blog.izs.me/post/2353458699/an-open-letter-to-javascript-leaders-regarding
[2]: http://inimino.org/~inimino/blog/javascript_semicolons
[3]: https://www.youtube.com/watch?v=gsfbh17Ax9I

### Commits

Just human readable prose. Starts in capital letter, describes an action with a verb. A commit _does_ one thing.
[Verb][Subject][Conditional and context...]

> Adds assets to Music.js
> Implements Bluetooth discovery
> Maps forgotten devices to a collection
> Implements destroy user saga
	
Use [amend](https://www.atlassian.com/git/tutorials/rewriting-history) for small changes.
For example if you leave a `console.log()` in the code and you want to remove it, you can't do it in a different commit.

When merging PRs into master, avoid merge commits :pray: `git pull --rebase`. Rewrite history. It will be merged as one.

### Pull Requests

Same thing as commits, be human, please. Use `[Tags like this][To describe feature sets][And dependant PRs]`

> [Alexa][Skill] Adds feedback when a command is not understood.

### Branches
As in repos `dash-case-is-awesome`. If you have many dependant one of another, please name it more specifically or give it a number
`lint-pull-requests-with-danger` or `lint-pull-requests-3`

### Classes

naming: **PascalCase**

```javascript
export class Switch extends Component {
...
```

### Functions

naming: **camelCase** and don't use "**_**"

```javascript
function getState () {
...
}
```

### Variables

naming: **camelCase** and don't use "**_**"

```javascript
	let myVar = 'my value'
```

### JSON & Objects

naming: **snake_case**

```javascript
{
	some_key: 'some value',
}
```

Example: i18n transations

### Files & Folders

Files and folders must be name after what they export.
Use `dash-case` if the file or folder does not have a main export.

```javascript
app
├── containers
├── components
|   ├── devices // export all device components -> no main export
|	|	├── Music.js // Music is a file that exports Music class
|   |	└── Bulb //Bulb is a folder that exports Bulb class in index
|			└── index.js
|...
```

### Imports
On the top of each files theres an order to write the imports.

1. Scripts (they don't have `from`)
2. Parts from modules
3. ProvidesModule
4. Relative paths

```javascript
import './lib/bootstrap'

import {
  Platform,
  Linking,
} from 'react-native'

import { i18n } from '%i18n'

import * as types from './actionTypes'
```

### Exports
Do not use `default` exports.

Just name the main export as the file it comes from. Then we'll know that it is the main export
of the file or filder it comes from. e.g: **Widget** folder or **Dialog.js** file.

Named exports are really helpful to export a bunch of features or components as one.
Check out **Layout** and **components**, the second one exports everything under Layout
with a single line: `export * from './Layout'`.

Use `@providesModule` for APIs that are going to be consumed from any part of the app. Prepend `%` so anyone knows that it belongs
to Yeti repo spec.

### Images

naming: **PascalCase**

```javascript
import * as Lifx from './lifx.png'
```

### Params

#### Case 1:
When params belong to the same field.

naming: obj

```javascript
// here id and params belongs to the charm field
	export const updateCharm = ({id, ...params}) => ({
 		type: types.UPDATE_CHARM,
  		id,
  		...params,
	})
```

#### Case 2:
When params doesn't belong to the same field.

naming: list

```javascript
// here customer and device are from different fields
export function mergeInfo (customer, device) {
...
}
```

#### Case 3:
When params doesn't belong to the same field but the order has to be specified in the function name.

naming: list

```javascript
/*
here device and routine are from different files but the order
is given in the function name
*/
export function appendDeviceToRoutine (device, routine) {
...
}
```
