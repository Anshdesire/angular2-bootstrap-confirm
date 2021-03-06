# Change Log

All notable changes to this project will be documented in this file. See [standard-version](https://github.com/conventional-changelog/standard-version) for commit guidelines.

<a name="0.6.0"></a>
# [0.6.0](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.5.2...v0.6.0) (2016-06-25)


### Features

* **customTemplate:** allow a custom template to be used for the popover ([ce7fec6](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/ce7fec6)), closes [#6](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues/6)



<a name="0.5.2"></a>
## [0.5.2](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.5.1...v0.5.2) (2016-06-23)


### Bug Fixes

* **isOpen:** fix isOpen attribute that when set would break this module ([fe5516d](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/fe5516d)), closes [#14](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues/14)



<a name="0.5.1"></a>
## [0.5.1](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.5.0...v0.5.1) (2016-06-22)



<a name="0.5.0"></a>
# [0.5.0](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.4.1...v0.5.0) (2016-06-17)


### Features

* **appendToBody:** add support for appendToBody ([6cfa171](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/6cfa171)), closes [#4](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues/4)
* **popoverClass:** allow a custom CSS class to be set on the popover ([e5baed9](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/e5baed9))
* **provide:** remove deprecated provide usage ([36f315f](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/36f315f))


### BREAKING CHANGES

* provide: angular RC2 or greater is now required to use this module



<a name="0.4.1"></a>
## [0.4.1](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.4.0...v0.4.1) (2016-05-19)


### Bug Fixes

* **angular-cli:** add main module export for angular-cli ([b8b77ac](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/b8b77ac))



<a name="0.4.0"></a>
## [0.4.0](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.3.3...v0.4.0) (2016-05-10)

### Features

**ConfirmOptions:** allow confirm options to be instantiated by angulars DI
    
### BREAKING CHANGES

* the constructor of ConfirmOptions now no longer takes an object of values.

This allows you to just pass `ConfirmOptions` directly to the providers of your app or component and angular will instantiate it for you. e.g.

```
providers: [ConfirmOptions], // previously angular would throw and you'd have to instantiate it yourself with useFactory
```

To migrate:

Before:
```
const options = new ConfirmOptions({
  focusButton: 'confirm'
});
```

After:
```
const options = new ConfirmOptions();
Object.assign(options, {
  focusButton: 'confirm'
});
```


<a name="0.3.3"></a>
## [0.3.3](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.3.2...v0.3.3) (2016-05-09)


### Bug Fixes

* dont bundle angular common module with the dist files([9b03f61](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/9b03f61))



<a name="0.3.2"></a>
## [0.3.2](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.3.1...v0.3.2) (2016-05-09)


### Bug Fixes

* fix typescript error that prevented the module from being imported([252e83e](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/252e83e))



<a name="0.3.1"></a>
## [0.3.1](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/0.3.0...v0.3.1) (2016-05-09)
* test release of the new publishing script and to update the npm readme


<a name="0.3.0"></a>
# [0.3.0](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/0.2.0...v0.3.0) (2016-05-07)


### Features

* **position:** rename PositionService to Position ([5c05e4e](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/5c05e4e)), closes [#11](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues/11)


### BREAKING CHANGES

* position: PositionService has now been renamed to Position. Use it like so:
```
import {Position} from 'angular2-bootstrap-confirm';
import {PositionService} from 'ng2-bootstrap/components/position';
provide(Position, {useClass: PositionService})
```



<a name="0.2.0"></a>
# [0.2.0](https://github.com/mattlewis92/angular2-bootstrap-confirm/compare/v0.1.0...v0.2.0) (2016-05-07)


### Features

* **angular2:** upgrade to angular2 RC1 ([d4d3c6b](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/d4d3c6b))
* **buttons:** allow hiding of the confirm / cancel buttons ([540b965](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/540b965)), closes [#10](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues/10)
* **position:** provide a bundled copy of the position service so ng2-bootstrap isn't required as a peer dependency ([37b295f](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/37b295f))
* allow usage without a module bundler by providing a standalone position bundle ([9ebae67](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/9ebae67)), closes [#8](https://github.com/mattlewis92/angular2-bootstrap-confirm/issues/8)
* add bootstrap v4 classes ([3f4959f2](https://github.com/mattlewis92/angular2-bootstrap-confirm/commit/3f4959f2))

### BREAKING CHANGES

* position: you now need to provide the position service for the directive to use like so:
```
import {provide} from '@angular/core';
import {bootstrap} from '@angular/platform-browser-dynamic';
import {Confirm, ConfirmOptions, PositionService} from 'angular2-bootstrap-confirm';
import {PositionService as Ng2PositionService} from 'ng2-bootstrap/components/position';
// Or if you don't want to depend on the ng2-bootstrap module, use the bundled position service:
// import {PositionService as Ng2PositionService} from 'angular2-bootstrap-confirm/position/position';
bootstrap(MyApp, [
   provide(PositionService, {useClass: Ng2PositionService})
]);
```
* angular2: a peer dependency of angular2 RC1 is now required



# 0.1.0
_Initial release_
