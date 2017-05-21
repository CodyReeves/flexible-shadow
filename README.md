# FlexibleShadow
A flexible SCSS mixin to generate shadow easily and efficiently.

## Example
http://codepen.io/CR-Design/pen/zKEdLN

# Installation
Add mixen yourself through manually implementing in your own Scss or


**Install Via Npm**

Add to package.json:

`"flexible-shadows": "git://github.com/CodyReeves/flexible-shadows.git"`

Add To Scss:

`@import {PATH}/node_modules/flexible-shadow/scss/flexibleshadow/main`

# Usage:

Examples of how you can write `@include`.

```
.example {
  @include shadow(1);
}

.example-1 {
  @include shadow(2, light);
}

.example-2 {
  @include shadow((
    $level: 4
    $text: text
  )...);
}

.example-3 {
  @include shadow($type, $level, $shadow-style, $text, $text-color);
}
```

## Arguments 

** Required **
- `$type` - light, dark, t-shadow (Can be more if more types are created)
- `$level` - 1, 2, 3, 4, or 5 (Each type has 5 levels, more can be created)

** Optional **
- `$shadow-style` - can be `inset` or `default`
- `$text` - set as `text` to  enable text shadow 
- `$text-color` - colors the text, NOTE: if args equal `$shadow-style: inset` and `$text: text`, `$inset-text-hack` has to be set to `true`, if it is not enabled result not guarenteed. 


### Defaut Values

```
@include shadow(
  $type: dark, 
  $level: 1, 
  $shadow-style: null, 
  $text: null, 
  $text-color: null
);
```

## Override Default Shadows

Default Shadows are set as a variable set as `!default`


**Dark Shadows**
- `$shadow-d-1`
- `$shadow-d-2`
- `$shadow-d-3`
- `$shadow-d-4`
- `$shadow-d-5`

**Light Shadows**
- `$shadow-l-1`
- `$shadow-l-2`
- `$shadow-l-3`
- `$shadow-l-4`
- `$shadow-l-5`

**Text Shadows**
- `$shadow-text-1`


## Adding More Shadows

Shadows are generated by a map. 

The variable `$shadows-custom` has been created to handle custom shadows 
This map merges with the default shadow map on compile. 

**Use:**
`$shadows-custom: ();`


### Writing The Custom Shadow Map

```
$shadows-custom: (
  custom: ( // Type of shadow 
    1: $shadow-c-1, // Give level as the key 
    2: 0 19px 38px rgba(0, 0, 0, 0.30), // Value as the shadow can have up to 2 shadow arguments
    3: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22),
    4: $shadow-c-4,
    5: $shadow-c-5
  )
)
```






