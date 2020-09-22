# CURRICULUM VITAE

## Name
Daniil Pasko
## Contact Info
**tel:** +375296041563<br>
**email:** danikp01@mail.ru<br>
**telegram:** https://t.me/greatly124
## Summary
My goal is to become a professional at the Front-End developing. I wish to increase my knowledge and skills through the instant practice.<br>
I have been interested in programming for a long time and since 2018 I have been studying the Front-End hard.<br>
I can describe myself as an attentive, plodding and easy-educable person.
## Skills
* HTML
* CSS
* JS
* React
    * React Hooks
* Redux
    * Redux Store
    * Redux - thunk
    * Redux Form
* React - Redux
* FLUX
* Python
* PHP
* Figma
## Code examples
### React Hooks

```javascript
import React, {useState} from 'react';

const TextArea = (props) => {

    const [newText, setNewText] = useState("");

    return (
        <textarea 
            type="text" 
            value={newText} 
            onChange={e => setNewText(e.target.value)} 
        />
    )
}

export default TextArea;
```

### Redux Form

```javascript
import style from "./AddPost.module.css";
import React from "react";
import {Field, reduxForm, reset} from "redux-form";
import {maxLengthCreator, required} from "../../utils/validators/validators";
import {Textarea} from "../Common/FormsFields/FormsFields";

const maxLength10 = maxLengthCreator(10);

const PostForm = (props) => {
    return (
        <form onSubmit={props.handleSubmit} className={style.addPost}>
            <Field
                placeholder={"New post..."}
                name="newPostText"
                component={Textarea}
                validate={[required, maxLength10]}
            />
            <button>Отправить</button>
        </form>
    )
}

let ReduxPostFrom = reduxForm({
    form: 'post',
})(PostForm)

const AddPostForm = (props) => {
    let onSubmit = (values, dispatch) => {
        props.addPost(values.newPostText);
        dispatch(reset('post'));
    }
    return (
        <ReduxPostFrom onSubmit={onSubmit}/>
    )
}

export default AddPostForm;
```

### FormsFields.js

```javascript
import React from "react";
import style from './FormsFields.module.css';

export const Textarea = ({input, meta, ...props}) => {
    const hasError = meta.touched && meta.error;
    return (
        <div className={`${style.formField} ${hasError ? style.error : ""}`}>
            <textarea {...input} {...props} />
            { hasError && <div>{meta.error}</div> }
        </div>
    )
}
```

### validators.js

```javascript
export const required = value => {
    if (!value) return "The field is required.";
    return undefined;
}

export const maxLengthCreator = (maxLength) => value => {
    if (value && value.length > maxLength) return `Max length is ${maxLength} symbols.`;
    return undefined;
}

export const minLengthCreator = (minLength) => value => {
    if (value && value.length < minLength) return `Min length is ${minLength} symbols.`;
    return undefined;
}
```

## Experience
Experience of developing a social network using the courses of *Dmitry Kuzedyubin* @it-kamasutra<br>
[My social network](https://github.com/Nedomorf/social-web)
<br>
I was the participant of the Huawei ICT Competition, Huawei Cup, Yandex Cup, Itransition Opener.
## Education
I am a student of the BNTU, the Faculty of Informational Technologies and Robotics now.<br>
I passed the courses of Dmitry Kuzedybin, was studying at the Itransition company.
## English
I have an experience in the translating of technical articles.<br>
Now I have the intermediate level (B1).
