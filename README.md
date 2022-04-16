# be-replaceable



```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content</div>
            </template>
        </slot>
        <overridable-template></overridable-template>
    #/shadow-root
    <template slot=overridable-template>
        <div>My Custom Content</div>
    </template>
</my-element>
```

Result: 

```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content</div>
            </template>
        </slot>
        <div>My Custom Content</div>
    #/shadow-root
    <template slot=overridable-template>
        <div>My Custom Content</div>
    </template>
</my-element>    
```

If no light child template is provided:

```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content</div>
            </template>
        </slot>
        <overridable-template></overridable-template>
    #/shadow-root
</my-element>
```

Result:

```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content</div>
            </template>
        </slot>
        <div>My Default Content</div>
    #/shadow-root
</my-element>
```

