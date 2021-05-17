[<< Back to Index](./index.md)

# FSXABaseAppLayout

1. [Introduction](#introduction)
2. [Usage](#usage)
3. [Properties](#properties)
4. [Methods](#methods)

## Introduction

The FSXABaseAppLayout is there to have a basic component to be able to implement the general layout of the app.
It provides different attributes, which should simplify the development significantly. These are described in this chapter.<br />
This component inherits all the attributes and methods of the [FSXABaseComponent](FSXABaseComponent.md).

## Usage

To use this base component a new class has to be created which extends the `FSXABaseAppLayout`.

```tsx
@Component
class Component extends FSXABaseAppLayout {}
```

## Properties

### `appState` - string

Returns the phase the app is.

Possible values are: `not_initialized`, `initializing`, `error`, `ready`.<br/>
Make sure that you render your layout corresponding to the appState.

- **not_initialized**: The app should not be displayed since no navigation-data,
  global-settings and page is fetched yet. If you are using SSR this will be only
  available on the SSR. So you do not need to display anything at all.

* **initializing**: The pattern-library is fetching the navigation-data and
  global-settings. If you are using SSR this will be only available on the SSR. So you
  not need to display anything at all.

- **error**: The pattern-library failed initializing itself. This can happen if the navigation-service is not available. The default slot will be always empty since the initialization failed.

- **ready**: The pattern-library did initialize and everything was loaded correctly.

### `appError` - Object

Returns the error if any occurred.<br />
Make sure to handle the error correctly.