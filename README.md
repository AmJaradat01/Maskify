# DataVeil

DataVeil is a library for masking sensitive data in various formats such as card numbers, email addresses, passwords, phone numbers, and more.

## Installation

```sh
npm install DataVeil
```

## Usage

```js
import { DataVeil } from './DataVeil';

// Mask card number with custom options
console.log(DataVeil.maskCardNumber('1234567812345678', { maskChar: '#', unmaskedStartDigits: 2, unmaskedEndDigits: 4 })); // 12##########1234

// Mask email address with custom options
console.log(DataVeil.maskEmail('example@example.com', { maskChar: '#', emailMaskVisibleChars: 3 })); // exa######@example.com

// Mask password with custom mask character
console.log(DataVeil.maskPassword('supersecret', { maskChar: '#' })); // ###########

// Mask phone number with custom options
console.log(DataVeil.maskPhoneNumber('123-456-7890', { maskChar: '#', unmaskedStartDigits: 2, unmaskedEndDigits: 1 })); // 12#-###-###0

// Mask substring with custom options
console.log(DataVeil.maskSubstring('hello world', 'world', { maskChar: '#', maskOnlyFirstOccurrence: true })); // hello #####

// Mask UUID with custom options
console.log(DataVeil.maskUUID('123e4567-e89b-12d3-a456-426614174000', { maskChar: '#', unmaskedStartDigits: 4, unmaskedEndDigits: 2 })); // 123e####-####-####-####-########00

// Mask JWT token with custom mask character
console.log(DataVeil.maskJWT('header.payload.signature', { maskChar: '#' })); // ######.######.########

// Mask JSON fields with custom options
const json = { card: '1234567812345678', email: 'example@example.com' };
console.log(DataVeil.maskJSON(json, ['card', 'email'], { maskChar: '#', emailMaskVisibleChars: 3 })); // { card: '12##########1234', email: 'exa######@example.com' }
```

## Testing

To run tests, use the following command:

```sh
npm test
```

## Contributing

Feel free to submit issues or pull requests for improvements and new features.

## License

This project is licensed under the MIT License.