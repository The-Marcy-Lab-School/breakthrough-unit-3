# Lesson: Class Based Components

## Short Response Questions

### Directions: Type out your response directly under each prompt.

1. What is the purpose of the constrctor in the following code snippet from a class based component:

```javascript
    constructor(props) {
        super(props);
        this.state = {
            email: '',
            password: '',
        };
        this.handleSubmit = this.handleSubmit.bind(this);
    }
```

2. Describe the purpose behind passing props to the function calls for `constructor()` and `super()`.

3. Based on your knowledge of functional programming and object-oriented programming, what might some of the benefits be of using functional components with hooks rather than class-based components?

4. Imagine a developer prefers to use class-based components in React and not hooks, is this allowable by the React community?
