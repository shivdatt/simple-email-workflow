
# Email workflow

What it does -

1. Builds HTML email
2. Inlines the CSS
3. Preview emails

## Getting Started

#### 1. ependencies
- Node.js (v10.x) with npm (v6.x) ([Install](https://nodejs.org/en/download/releases/))   
- Gulp.js (v3.x) ([Quick start](https://gulpjs.com/docs/en/getting-started/quick-start))

#### 2. Clone this repository
```
git clone 
cd email-workflow
```

#### 3. Setup npm config file / proxy


#### 4. Install packages  (Skip this step for now)

```
npm install
```
It will download all the dependencies and create node_modules folder.  

#### 5. Start build

```
npm start
```
The compiled and inlined output email will be in the `dist/` directory and can be previewed in browser at `http://localhost:8000`

## How to use

#### Creating templates
Reusable templates are stored in `src/templates` and layouts (combination of templates that builds an email) in `src/layouts`.
To include a template in layout, use the following syntax -

```
{% include "templates/header.html" %}
```

To define a block of dynamic content to be replaced by the email file, use the following syntax -

```
{% block CUSTOM_BLOCK_NAME %}{% endblock %}
```


#### Creating emails from templates

To create an email based off a template file, create a new file in the `src/emails/` directory (also with the `.html` file extension).

Specify which layout to use using the following syntax -

```
{% extends "default-layout.html" %}
```

To define the contents of a dynamic content block, use the following syntax -

```
{% block CUSTOM_BLOCK_NAME %} 
Content goes here
{% endblock %}
```


#### CSS

SASS files are stored in the `src/sass/` directory. 
You can create subdirectories within the SASS folder to hold any partials. Make sure to precede the name of a partial with an underscore, e.g. `_typography_.scss`.


## Local Build to preferred email platform 

#### Development
while building the template
go to email-template dir and 
run `npm start dev`

#### Build templates
once build is completed, run `npm start`

- go to `localhost:8000`
- open the email you just built

#### Copy the source
Copy the required source from your local build
- meta
- styles
- email body


#### Dynamic sections of the templates 

**Assets:** 
- add assets to src/assets folder and add link to the template (if you do not want to upload the images to the preferred CMS just yet)

**Layouts**
- This controls the layout of the email template

**Templates:** 
- Create/modify the segments of the templates 
- eg header, footer, sub-footer