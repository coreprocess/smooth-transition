# &lt;SmoothTransition /&gt;

![npm version](https://badgen.net/npm/v/smooth-transition?icon=npm&label)
![GitHub checks](https://badgen.net/github/checks/teamrevin/smooth-transition/publish?icon=github&label=GitHub)

`<SmoothTransition />` is a React component for elegantly transitioning between components. Its smooth fading effect and gliding height transition provides a seamless experience for your users as they switch between components.

## Installation

Use your favourite manager to install the [package](https://www.npmjs.com/package/smooth-transition):

```sh
yarn add smooth-transition
```

```sh
npm install smooth-transition --save
```

## Example

```ts
import { TextField, Typography } from "@mui/material";
import { SmoothTransition } from "smooth-transition";

export const Example = () => (
    <SmoothTransition
        render={[
            (state) => (
                <Typography ref={state != "leave" ? ref : undefined}>
                    {content}
                </Typography>
            ),
            (state) => (
                <TextField
                    ref={state != "leave" ? ref : undefined}
                    fullWidth
                    multiline
                    value={content}
                    onChange={onChange}
                />
            ),
        ]}
        active={!editMode ? 0 : 1}
        duration={500}
    />
);
```

## Properties

The component accepts the following properties:

-   `render: ((state: "enter" | "active" | "leave") => ReactNode)[]`: An array of render functions that return a `ReactNode`, representing the components that you want to transition between.
-   `active: number`: An integer specifying which component should be displayed.
-   `duration: number`: A number representing the duration of the transition in milliseconds.

## License

This library is licensed under the MIT license.

## Contributing

We welcome contributions to the smooth-transition library. To contribute, simply open a [pull request](https://github.com/teamrevin/smooth-transition/pulls) with your changes.

## Support

For issues or support, please open an issue on [GitHub](https://github.com/teamrevin/smooth-transition/issues).
