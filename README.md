# Box

The Box module simply boxes off content. This module is a fork of the [inuitcss Box module](https://github.com/inuitcss/objects.box).

## Dependencies

Px's Box module depends on three other Px and inuitcss modules:

* [settings.defaults](https://github.com/inuitcss/settings.defaults)
* [px-functions-design](https://github.sw.ge.com/pxc/px-functions-design)
* [px-clearfix-design](https://github.sw.ge.com/pxc/px-clearfix-design)

## Installation

Install this module and its dependencies using bower:

    bower install --save https://github.sw.ge.com/pxc/px-box-design.git

Once installed, `@import` into your project's Sass file in its Objects layer:

    @import "../px-box-design/objects.box";

#### A note about relative @import paths

Paths to a project's Bower dependencies differ depending on whether you are in the project itself (dependencies in some
a Bower managed directory in the project) vs. using the project 'downstream' (dependencies are siblings of the project).
Ideally we want to be able to 'build' in both cases without a lot of magic.

For Sass imports, can use the 'includePaths' option on the Grunt sass task to name a starting point to look for
relative paths. IncludePath 'bower_components/*' in the 'sass' task allows the actual @import paths in Sass files to start
with '../' so that they will resolve in either case described above and make editors happy.

## Import once

All rulesets are wrapped in the following `@if` statement:

    @if import-once('objects.box') { ... }

## Usage

These flags are available and, if needed, should be set to `true` prior to importing the module:

    $inuit-enable-box--flush
    $inuit-enable-box--tiny
    $inuit-enable-box--small
    $inuit-enable-box--large
    $inuit-enable-box--huge

The following dimension (padding) variables can be customized:

    $inuit-box-padding
    $inuit-box-padding--tiny
    $inuit-box-padding--small
    $inuit-box-padding--large
    $inuit-box-padding--huge

Basic usage of the Box object uses the required classes:

    <div class="box">
        Foo Bar Baz
    </div>

## Options

Other, optional classes can supplement the required base classes. These classes are available if the variable flags listed above are set to `true`:

* `box--flush`: remove all padding from boxes.
* `box--[tiny|small|large|huge]`: alter the padding on boxes.

For example:

    <div class="box box--large">
        Foo Bar Baz
    </div>
