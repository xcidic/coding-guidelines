---
title: "Angular 1 Style Guide"
date: 2017-07-10T18:41:37+07:00
draft: false
weight: 1
---

## Angular Team Endorsed
Special thanks to Igor Minar, lead on the Angular team, for reviewing, contributing feedback, and entrusting me to shepherd this guide.

## Purpose
*Opinionated Angular style guide for teams by [@john_papa](//twitter.com/john_papa)*

If you are looking for an opinionated style guide for syntax, conventions, and structuring Angular applications, then step right in. These styles are based on my development experience with [Angular](//angularjs.org), presentations, [Pluralsight training courses](http://app.pluralsight.com/author/john-papa) and working in teams.

The purpose of this style guide is to provide guidance on building Angular applications by showing the conventions I use and, more importantly, why I choose them.

>If you like this guide, check out my [Angular Patterns: Clean Code](http://jpapa.me/ngclean) course at Pluralsight which is a companion to this guide.

  [![Angular Patterns: Clean Code](https://raw.githubusercontent.com/johnpapa/angular-styleguide/master/a1/assets/ng-clean-code-banner.png)](http://jpapa.me/ngclean)

## Community Awesomeness and Credit
Never work in a vacuum. I find that the Angular community is an incredible group who are passionate about sharing experiences. As such, Angular expert Todd Motto and I have collaborated on many styles and conventions. We agree on most, and some we diverge. I encourage you to check out [Todd's guidelines](https://github.com/toddmotto/angular-styleguide) to get a sense for his approach and how it compares.

Many of my styles have been from the many pair programming sessions [Ward Bell](https://twitter.com/wardbell) and I have had. My friend Ward has certainly helped influence the ultimate evolution of this guide.

## See the Styles in a Sample App
While this guide explains the *what*, *why* and *how*, I find it helpful to see them in practice. This guide is accompanied by a sample application that follows these styles and patterns. You can find the [sample application (named modular) here](https://github.com/johnpapa/ng-demos) in the `modular` folder. Feel free to grab it, clone it, or fork it. [Instructions on running it are in its readme](https://github.com/johnpapa/ng-demos/tree/master/modular).

## Translations

[Translations of this Angular style guide](https://github.com/johnpapa/angular-styleguide/tree/master/a1/i18n) are maintained by the community and can be found here.

## Table of Contents

  1. [Single Responsibility]({{%relref "single-responsibility.md"%}})
  1. [IIFE]({{%relref "iife.md"%}})
  1. [Modules]({{%relref "modules.md"%}})
  1. [Controllers]({{%relref "controllers.md"%}})
  1. [Services]({{%relref "services.md"%}})
  1. [Factories]({{%relref "factories.md"%}})
  1. [Data Services]({{%relref "data-services.md"%}})
  1. [Directives]({{%relref "directives.md"%}})
  1. [Resolving Promises]({{%relref "resolving-promises.md"%}})
  1. [Manual Annotating for Dependency Injection]({{%relref "manual-annotating-for-dependency-injection.md"%}})
  1. [Minification and Annotation]({{%relref "minification-and-annotation.md"%}})
  1. [Exception Handling]({{%relref "exception-handling.md"%}})
  1. [Naming]({{%relref "naming.md"%}})
  1. [Application Structure LIFT Principle]({{%relref "application-structure-lift-principle.md"%}})
  1. [Application Structure]({{%relref "application-structure.md"%}})
  1. [Modularity]({{%relref "modularity.md"%}})
  1. [Startup Logic]({{%relref "startup-logic.md"%}})
  1. [Angular $ Wrapper Services]({{%relref "angular-wrapper-services.md"%}})
  1. [Testing]({{%relref "testing.md"%}})
  1. [Animations]({{%relref "animations.md"%}})
  1. [Comments]({{%relref "comments.md"%}})
  1. [JSHint]({{%relref "jshint.md"%}})
  1. [JSCS]({{%relref "jscs.md"%}})
  1. [Constants]({{%relref "constants.md"%}})
  1. [File Templates and Snippets]({{%relref "file-templates-and-snippets.md"%}})
  1. [Yeoman Generator]({{%relref "yeoman-generator.md"%}})
  1. [Routing]({{%relref "routing.md"%}})
  1. [Task Automation]({{%relref "task-automation.md"%}})
  1. [Filters]({{%relref "filters.md"%}})
  1. [Angular Docs]({{%relref "angular-docs.md"%}})
