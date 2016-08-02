# React Password Strength
A password strength indicator field using [zxcvbn](https://github.com/dropbox/zxcvbn) to calculate a password strength score.

## Install in your project

`npm install --save react-password-strength`

_Note: react/react-dom is a peer dependency. You should be using this in a React project._

## Run the example locally

- `npm install`
- `npm start`
- open [http://localhost:8080/](http://localhost:8080/)

## Using the tool

```
<ReactPasswordStrength
  minLength={5}
  minScore={2}
  scoreWords={['weak', okay', 'good', 'strong', 'stronger']}
  changeCallback={foo}
  inputProps={{ name="password_input" }}
/>
```

### Props

#### minLength (Default: 5)

- Minimum password length acceptable for password to be considered valid

#### minScore (Default: 2)

- Minimum score acceptable for password to be considered valid
- Scale from 0 - 4 denoting too guessable to very unguessable
- See [zxcvbn](https://github.com/dropbox/zxcvbn) docs for more detail

#### scoreWords (Default: ['weak', 'weak', 'okay', 'good', 'strong'])

- An array denoting the words used to describe respective score values in the UI

#### changeCallback

- Callback after input has changed (and score was recomputed)
- React Password Strength passes an object with the current app state (`score`, `password`, `isValid`) to the callback function

#### inputProps

- Props to pass down to the `input` element of the component. Things like `name`, `id`, etc
- Note that passing down `className` or other props used by the component will be overwritten and may cause unintended outcomes with React Password Strength

### Classes

_All styling is applied with CSS classes to allow custom styling and overriding._
- `ReactPasswordStrength` - namespace class and component wrapper
- `is-strength-{0-4}` - modifier class indicating password strength
- `ReactPasswordStrength-input` - password input field
- `is-password-valid` - modifier class indicating valid password
- `is-password-invalid` - modifier class indicating invalid password (only applies if password length > 0)
- `ReactPasswordStrength-strength-bar` - color bar indicating password strength
- `ReactPasswordStrength-strength-desc` - text indicating password strength