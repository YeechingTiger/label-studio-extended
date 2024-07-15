### Install for local development [The frontend and backend together for development]

You can run the latest Label Studio version locally without installing the package from pypi. 
#### Backend
```bash
# Install all package dependencies
pip install poetry
poetry install
poetry shell
# Run database migrations
python label_studio/manage.py migrate
python label_studio/manage.py collectstatic
# Start the server in development mode at http://localhost:8080
python label_studio/manage.py runserver
```

#### Frontend (keep building the frontend)
```bash
cd web
yarn install --frozen-lockfile

# Build the main Label Studio app continuously for development.
yarn watch
```
Develop url here: http://localhost:8080/

### Only customize the Frontend with example data
**Example: Customize the RichTextHtml component.**

Follow the link to run the Label Studio Frontend (Editor):  
https://github.com/uf-hobi-informatics-lab/label-studio-extended/tree/develop/web

```bash
yarn install --frozen-lockfile

# Run the frontend editor standalone.
yarn lsf:serve
```


```bash
cd web/libs/editor/src/env
```
In development.js, modify the example data.
```
const data = RichTextHtml;
```
Then, modify the components for customization in the web/libs/editor/src/tags/object/RichText.
