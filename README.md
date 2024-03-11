## How to setup Tailwind CSS

Step 1: Run the following commands

```
npm install -D tailwindcss
npx tailwindcss init
```

Step 2: Update tailwind.conf.js file to include this line:
```
content: ["*.html"],
```

Step 3: create src/input.css to include:
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Step 4: Include the src/output.css file to your html
```
<link href="./src/output.css" rel="stylesheet">
```

Step 5: Keep the index.html and index.js outside of the SRC directory

Step 6: Add this line into index.js to give access to the src folder
```
const path = require('path');
app.use('/src', express.static(path.join(__dirname, 'src')))
```

Step 7: Add this code into package.json
```
"scripts": {
    "start": "npx tailwindcss -i ./src/input.css -o ./src/output.css --watch && nodemon index.js"
  },
```

Step 8: Run the following command:
```
npm run start
```
