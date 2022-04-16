# be-replaceable


```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content</div>
            </template>
        </slot>
    #/shadow-root
    <template slot=overridable-template>
        <div>My Custom Content</div>
    </template>
</my-element>
```

Result:  A look is maintained in beReplaceable, with the host element serving as a key:

```TypeScript
export class MyElement{
    async someMethod(){
        const {templLookup} = await import('be-replaceable/be-replaceable.js');
        const templ = TemplLookup.get(this)['overridable-template'].deref();
    }
}
```

If no light child template is provided, **contrary** to what is shown above, the value of templ will be:

```html
<template slot=overridable-template>
    <div>My Custom Content</div>
</template>
```

But if a light child template *is* provided, such as shown above, the value of templ will be:

```html
<template slot=overridable-template>
    <div>My Custom Content</div>
</template>
```