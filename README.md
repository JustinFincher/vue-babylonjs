# Vue-BabylonJS

Create high quality 3D graphics in the web as easily as writing HTML and CSS.

Quickly make a 3D animation:

![3D Animation](https://thumbs.gfycat.com/WhiteTangibleIndianspinyloach-size_restricted.gif)

It's this easy:

```pug
Scene
  Camera
  HemisphericLight(diffuse="#0000FF")
  Entity(:position="[0, 0, 5]")
    Animation(property="rotation.x" :duration="5")
      Key(frame="0%" :value="0")
      Key(frame="100%" :value="Math.PI * 2")
    Animation(property="rotation.y" :duration="5" :end="Math.PI * 2")
    Animation(property="rotation.z" :duration="5" :end="Math.PI * 2")
    PointLight(diffuse="#FF0000")
    Box(v-for="position in boxes" :position="position")
```

## API Documentation
See the [documentation website](https://beg-in.github.io/vue-babylonjs/) (work in progress)

## Getting Started

### Installation

```shell
$ npm install vue-babylonjs
```

**or**:

```shell
$ yarn add vue-babylonjs
```

In your script:

```js
let Vue = require('vue');
Vue.use(require('vue-babylonjs'));
```

In your template (Pug):

```pug
Scene
  Camera
  HemisphericLight
  Box(:position="[0, 0, 5]")
```

**or**:

(HTML)

```html
<Scene>
  <Camera>
  <HemisphericLight>
  <Box :position="[0, 0, 5]">
</Scene>
```
## Updates

[Subscribe to the mailing list issue to keep up with important updates](https://github.com/Beg-in/vue-babylonjs/issues/1)

## About

Vue-BabylonJS is a 3D graphics component plugin for [Vue.js](https://vuejs.org/) powered by [BabylonJS](https://www.babylonjs.com/).
Vue-BabylonJS draws inspiration from A-Frame, but can be more performant with the exclusion of DOM manipulation and has closer ties to JavaScript through property binding syntax in Vue. Compared to ReactVR which uses A-Frame, Vue-BabylonJS has the potential for higher performance, more organized and decoupled components, and a higher-quality rendering engine. 

[See the discussion on the HTML 5 Game Dev Forums](http://www.html5gamedevs.com/topic/35379-vue-integration-like-a-frame/?tab=comments#comment-204093)

### Rationale

We use BabylonJS because it is the most efficient, most feature-rich, and most modern WebGL graphics library available. The addition of Vue makes the engine reactive and development becomes easier to reason about and organize. Out-of-the-box mobile support and sensible defaults make getting started a breeze.

The underlying engine is easily accessible to give pros the tools to tweak every aspect of BabylonJS. The organizational structure of the library is a Component-Entity-System and the Entity component contains many powerful features such a matrix transformation to allow for interaction with the Scene graph like a group of HTML divs. Powerful tools are available such as an integrated reactive property system that enables modifying 3D objects within templates and a Shader component that makes adding WebGL shaders easy.

## Contributing

See `CONTRIBUTING.md`
