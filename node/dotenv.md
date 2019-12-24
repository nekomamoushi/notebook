# dotenv

## Installation

```
# with npm
npm install dotenv

# or with Yarn
yarn add dotenv
```

Install also type definitions for dotenv 

```
npm install @types/dotenv
```
## Usage

First, import dotenv

```
import dotenv from "dotenv";
```

Load your env file

```
dotenv.config();
```

Create a .env file in the root directory of your project.

Add environment-specific variables on new lines in the form of NAME=VALUE. 

```
DB_HOST=localhost
DB_USER=root
DB_PASS=s1mpl3
```

Now `process.env` has the keys and values you defined in your .env file.

```
const myenv = {
  host: process.env.DB_HOST,
  username: process.env.DB_USER,
  password: process.env.DB_PASS
}
```
