# be-replaceable [TODO]



```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content I</div>
                <div>My Default Content II</div>
            </template>
        </slot>
        <overridable-template></overridable-template>
    #/shadow-root
    <template slot=overridable-template>
        <div>My Custom Content I</div>
        <div>My Custom Content II</div>
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
        <div>My Custom Content I</div>
        <div>My Custom Content II</div>
    #/shadow-root
    <template slot=overridable-template>
        <div>My Custom Content I</div>
        <div>My Custom Content II</div>
    </template>
</my-element>    
```

If no light child template is provided:

```html
<my-element>
    #shadow-root
        <slot name=overridable-template be-replaceable>
            <template>
                <div>My Default Content I</div>
                <div>My Default Content II</div>
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
                <div>My Default Content I</div>
                <div>My Default Content II</div>
            </template>
        </slot>
        <div>My Default Content I</div>
        <div>My Default Content II</div>
    #/shadow-root
</my-element>
```

