scss folder=> contains all the styles for out project
we will extract it as a separate npm package which will be used by across all teams
scss-> src => all the source code

scss-> src -> foundation => it will contain the style guide for our design system
this will have fundamentals of the system

Advanced React For Enterprise
Section 1 Design System: 
 Imagine working for a company (Shopify), there is a web , ios and andriod applications.
 Developers on the web application do not have a designer so they will improvise the components, use bootstrap and design whatever they need.
 Similarly developers on andriod will use the native components tweek the css and design what they like ,same thing with IOS developers.

 When customer uses web app and switches to mobile app, customer would be confused because the experience would be completely different.
 So companies decides to get bunch of designers, product managers and engineers who will collaborate together to create a system 
  that would be  consistent across differnt platforms.

 Design System : 
    A set of agreements to define how a company or set of people working together would build product

Foundations of design system
    Accessibility for all people
    Internationalization
    Voice and the tone
    Grammer and content 
    Fonts used in the company

    Consistency is the key

Atomic Design Principles (just one methodology to desing system)
    Atoms : tiniest unit (e.g label very small but can exist on its own , Input, button, logo etc)
    Molecules : Combinations of atoms (e.g. Search (lebel, input and button))
    Organisms : Many molecules and atoms (Navbar, blogpost, Footer)
    Templates 
    Pages
Example Design systems
https://carbondesignsystem.com/ => Created by IBM, can check guidelines and components with actual implementation of the design system
https://react.fluentui.dev/?path=/docs/concepts-introduction--page => by Microsoft
https://www.figma.com/design-systems/
 --------------------------------------------------------------------------------------------------------------
Section 2 CSS Architecture
Checkilist:
    1. Organised => fixed code structure
    2. No specificity issues (css from one component should not coflict with other component)
    3. Atomic design Principles
    4. Easy to understand (comments and variables)
    5. customizable/ themeable
    6. Reusable across teams/projects

 --------------------------------------------------------------------------------------------------------------
Define mixins:
    As our design system grows, we will realize that code duplication is unavoidable. Thats why we have mixins.
    We want to make our code more reusable

    Media Query in CSS : essential for mobile device, mobile responsiveness
    Landcap mode : width is wider than height

* One important part of design system is "Spacing".
 --------------------------------------------------------------------------------------------------------------
 Global.scss 

 To set this file we need to install a packege for normalize.scss
 For that we go to scss and do 
 install yarn for windows
 yarn init -y
 yarn add normalize-scss
 //normalize import is needed to normalize default HTML elements across all browsers
 --------------------------------------------------------------------------------------------------------------
 Stylelint and Prettier: consistent code base , rules for indetation, variables declaration and mixins declaration, how to use map etc
 Stylelint : focus on how the code works, e.g. how mixin works
            stylelint-config-sass-guidelines -> start guide for scalable and maintainable sass
 prettier : focus on formatting
            stylelint-config-prettier -> formatting

yarn add --dev stylelint stylelint-config-sass-guidelines stylelint-config-prettier stylelint-prettier prettier 

in package.json we add
"scripts": {
    "lint": "stylelint './**/*.scss'" -> lint all files in all folders and subfolders with .scss extension
  }
 --------------------------------------------------------------------------------------------------------------
 Setup husky and pre-commit hooks
Developers may not remember to run lint-fix to format the code properly or to adhere to code standards.
To automate process of running lint fix after the developer is done with his changes, we need two packages
husky-> will help us to use git hooks if we want to run a command before/after we commit/push the changes
lint-staged -> to run husky only on files that are staged before commiting
what hooks we are interested in needs to be defined in package.json
yarn add --dev husky lint-staged
 --------------------------------------------------------------------------------------------------------------
 Dummy data: https://dummyjson.com/products
