# @codebayu/style-variants

The Package for creating dynamic and reusable styles in React Native App

## Installation

```bash
# npm
npm install @codebayu/style-variants

# yarn
yarn add @codebayu/style-variants
```

## Usage

```tsx
import { sv } from '@codebayu/style-variants';

export default function ReusableButton({
  children,
  color,
  size,
  style,
  ...rest
}) {
  const buttonStyle = buttonVariant({ color, size });
  const textStyle = textVariant({ color, size });
  return (
    <Pressable style={[buttonStyle, style]} {...rest}>
      <Text style={textStyle}>{children}</Text>
    </Pressable>
  );
}

const textVariant = sv({
  base: {
    fontWeight: '600',
  },
  variants: {
    color: {
      primary: {
        color: 'green',
      },
      secondary: {
        color: 'blue',
      },
      ghost: {
        color: 'black',
      },
    },
    size: {
      small: {
        fontSize: 14,
      },
      medium: {
        fontSize: 16,
      },
      large: {
        fontSize: 18,
      },
    },
  },
  defaultVariants: {
    color: 'primary',
    size: 'medium',
  },
});

const buttonVariant = sv({
  base: {
    height: 'auto',
    alignItems: 'center',
  },
  variants: {
    color: {
      primary: {
        backgroundColor: '#eee',
        padding: 17,
        fontWeight: '600',
        borderRadius: 5,
        width: '100%',
        borderWidth: 1,
        borderColor: '#eee',
      },
      secondary: {
        backgroundColor: '#e3e3e3',
        padding: 17,
        fontWeight: '600',
        borderRadius: 5,
        width: '100%',
        borderWidth: 1,
        borderColor: '#eee',
      },
      ghost: {
        backgroundColor: 'transparent',
      },
    },
  },
  defaultVariants: {
    color: 'primary',
  },
});
```

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE](LICENSE) file for details.
