---
title: "ion-textarea"
hide_table_of_contents: true
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
import TOCInline from '@theme/TOCInline';

import Props from '@site/static/auto-generated/textarea/props.md';
import Events from '@site/static/auto-generated/textarea/events.md';
import Methods from '@site/static/auto-generated/textarea/methods.md';
import Parts from '@site/static/auto-generated/textarea/parts.md';
import CustomProps from '@site/static/auto-generated/textarea/custom-props.md';
import Slots from '@site/static/auto-generated/textarea/slots.md';

<head>
  <title>Ionic Textarea Component and CSS Properties for Multi-Line Input</title>
  <meta name="description" content="Textarea is for multi-line input. The component accepts native textarea attributes in addition to Ionic properties. Read to learn about use and CSS elements." />
</head>

import EncapsulationPill from '@components/page/api/EncapsulationPill';

<EncapsulationPill type="scoped" />

<h2 className="table-of-contents__title">Contents</h2>

<TOCInline
  toc={toc}
  maxHeadingLevel={2}
/>



The textarea component is used for multi-line text input. A native textarea element is rendered inside of the component. The user experience and interactivity of the textarea component is improved by having control over the native textarea.

Unlike the native textarea element, the Ionic textarea does not support loading its value from the inner content. The textarea value should be set in the `value` attribute.

The textarea component accepts the [native textarea attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) in addition to the Ionic properties.

## Interfaces

### TextareaChangeEventDetail

```typescript
interface TextareaChangeEventDetail {
  value?: string | null;
}
```

### TextareaCustomEvent

While not required, this interface can be used in place of the `CustomEvent` interface for stronger typing with Ionic events emitted from this component.

```typescript
interface TextareaCustomEvent extends CustomEvent {
  detail: TextareaChangeEventDetail;
  target: HTMLIonTextareaElement;
}
```



## Usage

<Tabs groupId="framework" defaultValue="angular" values={[{ value: 'angular', label: 'Angular' }, { value: 'javascript', label: 'Javascript' }, { value: 'react', label: 'React' }, { value: 'stencil', label: 'Stencil' }, { value: 'vue', label: 'Vue' }]}>

<TabItem value="angular">

```html
<!-- Default textarea -->
<ion-textarea></ion-textarea>

<!-- Textarea in an item with a placeholder -->
<ion-item>
  <ion-textarea placeholder="Enter more information here..."></ion-textarea>
</ion-item>

<!-- Textarea in an item with a floating label -->
<ion-item>
  <ion-label position="floating">Description</ion-label>
  <ion-textarea></ion-textarea>
</ion-item>

<!-- Disabled and readonly textarea in an item with a stacked label -->
<ion-item>
  <ion-label position="stacked">Summary</ion-label>
  <ion-textarea
    disabled
    readonly
    value="Ionic enables developers to build performant, high-quality mobile apps.">
  </ion-textarea>
</ion-item>

<!-- Textarea that clears the value on edit -->
<ion-item>
  <ion-label>Comment</ion-label>
  <ion-textarea clearOnEdit="true"></ion-textarea>
</ion-item>

<!-- Textarea with custom number of rows and cols -->
<ion-item>
  <ion-label>Notes</ion-label>
  <ion-textarea rows="6" cols="20" placeholder="Enter any notes here..."></ion-textarea>
</ion-item>
```


</TabItem>


<TabItem value="javascript">

```html
<!-- Default textarea -->
<ion-textarea></ion-textarea>

<!-- Textarea in an item with a placeholder -->
<ion-item>
  <ion-textarea placeholder="Enter more information here..."></ion-textarea>
</ion-item>

<!-- Textarea in an item with a floating label -->
<ion-item>
  <ion-label position="floating">Description</ion-label>
  <ion-textarea></ion-textarea>
</ion-item>

<!-- Disabled and readonly textarea in an item with a stacked label -->
<ion-item>
  <ion-label position="stacked">Summary</ion-label>
  <ion-textarea
    disabled
    readonly
    value="Ionic enables developers to build performant, high-quality mobile apps.">
  </ion-textarea>
</ion-item>

<!-- Textarea that clears the value on edit -->
<ion-item>
  <ion-label>Comment</ion-label>
  <ion-textarea clear-on-edit="true"></ion-textarea>
</ion-item>

<!-- Textarea with custom number of rows and cols -->
<ion-item>
  <ion-label>Notes</ion-label>
  <ion-textarea rows="6" cols="20" placeholder="Enter any notes here..."></ion-textarea>
</ion-item>
```


</TabItem>


<TabItem value="react">

```tsx
import React, { useState } from 'react';
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonTextarea, IonItem, IonLabel, IonItemDivider, IonList } from '@ionic/react';

export const TextAreaExamples: React.FC = () => {
  const [text, setText] = useState<string>();

  return (
    <IonPage>
      <IonHeader>
        <IonToolbar>
          <IonTitle>TextArea Examples</IonTitle>
        </IonToolbar>
      </IonHeader>
      <IonContent>
        <IonList>
          <IonItemDivider>Default textarea</IonItemDivider>          
          <IonItem>
            <IonTextarea value={text} onIonChange={e => setText(e.detail.value!)}></IonTextarea>
          </IonItem>

          <IonItemDivider>Textarea in an item with a placeholder</IonItemDivider>
          <IonItem>
            <IonTextarea placeholder="Enter more information here..." value={text} onIonChange={e => setText(e.detail.value!)}></IonTextarea>
          </IonItem>

          <IonItemDivider>Textarea in an item with a floating label</IonItemDivider>
          <IonItem>
            <IonLabel position="floating">Description</IonLabel>
            <IonTextarea value={text} onIonChange={e => setText(e.detail.value!)}></IonTextarea>
          </IonItem>

          <IonItemDivider>Disabled and readonly textarea in an item with a stacked label</IonItemDivider>
          <IonItem>
            <IonLabel position="stacked">Summary</IonLabel>
            <IonTextarea
              disabled
              readonly
              value={text} onIonChange={e => setText(e.detail.value!)}>
            </IonTextarea>
          </IonItem>

          <IonItemDivider>Textarea that clears the value on edit</IonItemDivider>
          <IonItem>
            <IonLabel>Comment</IonLabel>
            <IonTextarea clearOnEdit={true} value={text} onIonChange={e => setText(e.detail.value!)}></IonTextarea>
          </IonItem>

          <IonItemDivider>Textarea with custom number of rows and cols</IonItemDivider>
          <IonItem>
            <IonLabel>Notes</IonLabel>
            <IonTextarea rows={6} cols={20} placeholder="Enter any notes here..." value={text} onIonChange={e => setText(e.detail.value!)}></IonTextarea>
          </IonItem>
        </IonList>
      </IonContent>
    </IonPage>
  );
};
```


</TabItem>


<TabItem value="stencil">

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'textarea-example',
  styleUrl: 'textarea-example.css'
})
export class TextareaExample {
  render() {
    return [
      // Default textarea
      <ion-textarea></ion-textarea>,

      // Textarea in an item with a placeholder
      <ion-item>
        <ion-textarea placeholder="Enter more information here..."></ion-textarea>
      </ion-item>,

      // Textarea in an item with a floating label
      <ion-item>
        <ion-label position="floating">Description</ion-label>
        <ion-textarea></ion-textarea>
      </ion-item>,

      // Disabled and readonly textarea in an item with a stacked label
      <ion-item>
        <ion-label position="stacked">Summary</ion-label>
        <ion-textarea
          disabled
          readonly
          value="Ionic enables developers to build performant, high-quality mobile apps.">
        </ion-textarea>
      </ion-item>,

      // Textarea that clears the value on edit
      <ion-item>
        <ion-label>Comment</ion-label>
        <ion-textarea clearOnEdit={true}></ion-textarea>
      </ion-item>,

      // Textarea with custom number of rows and cols
      <ion-item>
        <ion-label>Notes</ion-label>
        <ion-textarea rows={6} cols={20} placeholder="Enter any notes here..."></ion-textarea>
      </ion-item>
    ];
  }
}
```


</TabItem>


<TabItem value="vue">

```html
<template>
  <!-- Default textarea -->
  <ion-textarea></ion-textarea>

  <!-- Textarea in an item with a placeholder -->
  <ion-item>
    <ion-textarea placeholder="Enter more information here..."></ion-textarea>
  </ion-item>

  <!-- Textarea in an item with a floating label -->
  <ion-item>
    <ion-label position="floating">Description</ion-label>
    <ion-textarea></ion-textarea>
  </ion-item>

  <!-- Disabled and readonly textarea in an item with a stacked label -->
  <ion-item>
    <ion-label position="stacked">Summary</ion-label>
    <ion-textarea
      disabled
      readonly
      value="Ionic enables developers to build performant, high-quality mobile apps.">
    </ion-textarea>
  </ion-item>

  <!-- Textarea that clears the value on edit -->
  <ion-item>
    <ion-label>Comment</ion-label>
    <ion-textarea clear-on-edit="true"></ion-textarea>
  </ion-item>

  <!-- Textarea with custom number of rows and cols -->
  <ion-item>
    <ion-label>Notes</ion-label>
    <ion-textarea rows="6" cols="20" placeholder="Enter any notes here..."></ion-textarea>
  </ion-item>
</template>

<script>
import { IonItem, IonLabel, IonTextarea } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { IonItem, IonLabel, IonTextarea }
});
</script>
```


</TabItem>

</Tabs>

## Properties
<Props />

## Events
<Events />

## Methods
<Methods />

## CSS Shadow Parts
<Parts />

## CSS Custom Properties
<CustomProps />

## Slots
<Slots />