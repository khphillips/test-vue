# test-vue

## Project setup
You will need to install node first (be sure to also include npm) (https://nodejs.org/en/download/)
Then from the commandline run the following to clone the repo, install the dependencies. 
```
git clone https://github.com/khphillips/test-vue.git
cd test-vue
npm install
```
Cool, now you have the directory and can start fooling around. 

### Compiles and hot-reloads for development
```
npm run serve
```

This will compile the app and then fire up a dev server. Go to the address in your browser, http://localhost:8080/ 

Everytime you save changes to the code, it will automatically recomile and refresh the browser. 

You will want to open developer tools to the console to help debug. You can also install the Chrome extension : https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd

### Think in terms of components

Maybe start by checking out the "Dashboard" view in "src/views/Dashboard.vue". This view is a "component". There's two parts to it. The "template" which is the html and DOM structure. And then the "script" where all the code goes. If you follow along on the vuejs "getting started site" you can use the Dashboard as your test. The main difference is the examples they give will looks like this:

```
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: 'You loaded this page on ' + new Date().toLocaleString()
  }
})
```

That's as if you are using vue without components. To do the samples within our Dashboard view you will look for the "data" section in the script and modify that instead of the whole var app2 stuf... it will look like this:

```
export default {
	name: 'Dashboard',
	props:[]
	data: {
	    message: 'You loaded this page on ' + new Date().toLocaleString();
	},
	computed:{

	},
	methods: {

	},
	watch: {

	}
}
```

I would recommend the doing some of the getting started stuff on the vuejs site: https://vuejs.org/v2/guide/index.html You don't need to worry about the 'installation' part since everything is already set up. 

### UI & CSS

This demo is set up to use Vuetify. https://vuetifyjs.com/en/introduction/why-vuetify Document is excellent. You can use and play with any of the components. For example add an alert to our dashboard: https://vuetifyjs.com/en/components/alerts Paste the code below into the template section of the Dashboard.vue file. Maybe just below the <v-container fluid>. A template can only have 1 root element, so it needs to be inside the v-container element in this case.  

```
<v-alert type="info" >
	I'm a alert with a <strong>type</strong> of info
</v-alert>
```

#### SASS & CSS

Vuetify is quite flexible and a lot of the changes you need can be made using options within the component. However you may need to override or add new CSS. This app is set up to use sass. You can create and modify the scss files in the /src/sass/ folder. 

#### Icons

I've got the FontAwesome icons loaded in the demo. To use them, use the vuetify component ```v-icon``` along with the font-awesome class tag. For example: 

```
<v-icon>fas fa-bomb</v-icon>
```

#### Responsive

This app is already fully responsive. It uses the vuetify grid system. Starts with a v-container inside is a v-row and inside those is v-col. Checkout the dashboard layout. The v-cols have attributes for sm md lg. These are the number of columns this item will stretch on those given screen sizes. The default is 'cols' for mobile screens. 

```
<v-col cols="12" md="3" sm="6">
	Some content
</v-col>
```

In the example above, the column on mobile will be 12 meaning is spans the full width of a 12 column row - 100%. On a small screen (tablets) it will only span 6 columns - 50% of the width of the row. On md screens and above they only span 3 columns - 25% of the width of the row. More info on the vuetify grid system is here: https://vuetifyjs.com/en/components/grids

### Compiles and minifies for production
```
npm run build
```

