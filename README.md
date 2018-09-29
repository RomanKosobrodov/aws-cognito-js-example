# aws-cognito-js-example

Example javascript application that uses AWS Cognito to:
* add a new user to the pool
* sign the user in
* sign the user out
* change password
* reset forgotten password
* delete the user

## Motivation

Examples provided in the [AWS Cognito Developer Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/using-amazon-cognito-user-identity-pools-javascript-examples.html) are not always easy to follow. This minimalistic application was created to fill this gap.

## Prerequisites

It is recommended that you create a new Cognito User pool for this example application.
If you are new to Cognito you might want to check AWS ["Getting Started"](https://aws.amazon.com/cognito/getting-started/) guide.

While creating the user pool make sure you:
1. Enable signing in with a user name ("Users can use a username and optionally multiple alternatives to sign up and sign in"). Check the box to "Also allow sign in with verified email address"
1. Select email and preffered_username as required attributes
1. Check "Allow users to sign themselves up" on the policies page
1. When asked "Do you want to require verification of emails or phone numbers?" select Email
1. Disable advanced security features
1. Choose "code" as user verification method
1. Create an application that can access this user pool. IMPORTANT: disable application secrets. Javascript API does not support client secrets. 
1. Copy your Pool ID and Application ID - you will need to provide them to our application.

## Dependencies

1. amazon-cognito-identity.min.js is included in the repository. It is now part of [AWS Amplify](https://github.com/aws-amplify/amplify-js/tree/master/packages/amazon-cognito-identity-js) Javascript SDK.
1. bootstrap (requires jQuery) for the UI.

## Code

There are three files in the project:
* index.html 
* js/authentication.js is a thin wrapper for the SDK that makes using it a bit easier
* js/user-interface.js contains page rendering code, DOM event handlers etc.

## How to use

Clone the repo and open index.html in the browser. The code is tested on Chrome and Firefox.
Click Credentials in the navigation bar and provide your user pool ID and app ID. They are stored in the browser local storage and will persist, so you might want to clear your secrets ("Forget" button) when you're done using it.

You might need a disposable email service like [Guerilla Mail](https://www.guerrillamail.com/) or similar to create new users.

## Credits

Icons by [Julian Schnaars](https://www.iconfinder.com/iconsets/female-styles)

