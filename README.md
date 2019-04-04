# TodoListWithFiltering
Make Todo List with Pending and Done Filtering

1. There should be a Textbox and Button

![alt text](https://github.com/poojathakor/TodoListWithFiltering/blob/master/todoNormal/a.png)

2. Once we enter Text and Click on Add Button, It should be added in the List of Pending Items having Checkbox

![alt text](https://github.com/poojathakor/TodoListWithFiltering/blob/master/todoNormal/d.png)

3. If we check any of the checkbox of Panding Items list, It should be moved in Done Items

![alt text](https://github.com/poojathakor/TodoListWithFiltering/blob/master/todoNormal/e.png)

## Build Setup
[VUE CLI](https://cli.vuejs.org/guide/installation.html)

``` bash
# install VUE CLI
npm install -g @vue/cli

# you can check version
vue --version

# set name, version, description, author as per requirement

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# to install Bootstrap
npm i vue bootstrap-vue bootstrap
```

## Integrate Bootstrap
[Bootstrap Vue](https://bootstrap-vue.js.org/docs)
``` js
// add in main.js
import BootstrapVue from 'bootstrap-vue'
import "bootstrap/dist/css/bootstrap.min.css"
import "bootstrap-vue/dist/bootstrap-vue.css"
 
Vue.use(BootstrapVue);

```
