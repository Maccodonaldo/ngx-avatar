# # &lt;ngx-avatar&gt;
[![Build Status](https://travis-ci.org/HaithemMosbahi/angular2-avatar.svg?branch=master)](https://travis-ci.org/HaithemMosbahi/angular2-avatar)

A universal avatar component for Angular 2+ applications that fetch / generates avatar based on the informations you have about the user. The component has a fallback system that if for example an invalid Facebook ID is used it will try google ID and so on.

You can use this component whether you have a single source or a multiple avatar sources. In this case the fallback system will fetch the first valid avatar.

Moreover, the component can shows name initials or simple value as avatar.

![Angular Avatar component preview](demo/demo.png)


 Supported avatar sources:

 * Facebook
 * Google
 * Twitter
 * Skype
 * Gravatar
 * Custom image
 * name initials
 * value

 The fallback system uses the same order as the above source list, Facebook has the highest priority, if it fails, google source will be used, and so on.

## Installation

Install avatar component using [NPM](https://www.npmjs.com/)::

```bash
$ npm install ngx-avatar --save
```
Or [download as ZIP](https://github.com/HaithemMosbahi/ngx-avatar/archive/master.zip).


## Usage

1. Import AvatarModule :

Once you have installed ngx-avatar, you can import it in your `AppModule`:

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your AvatarModule
import { AvatarModule } from 'ngx-avatar';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    // Specify AvatarModule as an import
    AvatarModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
2. Start using it:

Once the AvatarModule is imported, you can start using the component in your Angular application:

```html
<ngx-avatar></ngx-avatar>
```
## Examples

```html
<ngx-avatar facebookId="1508319875"></ngx-avatar>
<ngx-avatar googleId="1508319875"></ngx-avatar>
<ngx-avatar twitterId="1508319875"></ngx-avatar>
<ngx-avatar name="Jhon Doe"></ngx-avatar>
<ngx-avatar value="75%"></ngx-avatar>

<ngx-avatar source="facebook" skypeId="skype" googleId="google" name="Haithem Mosbahi" custom="assets/custom.jpg" value="28%" initials facebookId="100008343750912" twitterId="twitter" gravatarId="gravatar" size="100" [round]="true"></ngx-avatar>

```

## Options

|   Attribute   |      Type      | Default |                                              Description                                               |
| ------------- | ----------------- | ------- | ------------------------------------------------------------------------------------------------------ |
| `facebook-id` | *string* |         |                                                                                                        |
| `twitter-id` | *string* |         |                                                                                                        |
| `google-id`   | *string*             |         |                                                                                                        |
| `skype-id`    | *string*          |         |                                                                                                        |
| `name`        | *string*          |         | Will be used to generate avatar based on the initials of the person                                    |
| `value`       | *string*          |         | Show a value as avatar                                                                                 |
| `color`       | *string*          | random  | Give the background a fixed color with a hex like for example #FF0000 |
| `fgColor`     | *string*          | #FFF  | Used in combination with `name` and `value`. Give the text a fixed color with a hex like for example #FF0000 |
| `size`        | *number*             | 50      | Size of the avatar                                                                                     |
| `textSizeRatio` | *number*             | 3      | For text based avatars the size of the text as a fragment of size (size / textSizeRatio)                                 |
| `round`       | *bool*            | true   | Round the avatar corners                                                                               |
| `src`         | *string*          |         | Fallback image to use                                                                                  |
| `style`         | *object*          |         | Style that will be applied on the root element

## Development

To generate all `*.js`, `*.d.ts` and `*.metadata.json` files:

```bash
$ npm run build
```

To lint all `*.ts` files:

```bash
$ npm run lint
```

## License

MIT © [Haithem Mosbahi](mailto:elmosbahihaithem@gmail.com)
