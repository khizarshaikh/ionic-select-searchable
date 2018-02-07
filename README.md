# Ionic Select with Searchbar
An Ionic component similar to `ion-select`, that allows to search items, including async search and infinite scrolling.

# Contents
* [Demo](#demo)
* [Download](#download)
* [Getting started](#demo)
* [API](#api)
* [Development](#development)

## Demo
* [Github demo app](https://github.com/eakoriakin/select-searchable-demo)
* [Plunker](http://plnkr.co/edit/YzCBKS?p=preview)

### iOS
![iOS Demo 1](demo/ios-1.png)
![iOS Demo 2](demo/ios-2.png)

### Android
![Android Demo 1](demo/android-1.png)
![Android Demo 2](demo/android-2.png)

## Download
Download it using npm:

`npm install ionic-select-searchable --save`

## Getting started

1. Import `SelectSearchable` to your main app module.
```
import { NgModule } from '@angular/core';
import { SelectSearchableModule } from 'ionic-select-searchable';

@NgModule({
    ...
    imports: [
        ...
        SelectSearchableModule
    ],
    ...
})
export class AppModule { }

```
2. Add `SelectSearchable` to your component template.
```
<ion-item>
    <select-searchable
        title="Port"
        [(ngModel)]="port"
        [items]="ports"
        itemValueField="id"
        itemTextField="name"
        [canSearch]="true"
        (onChange)="portChange($event)">
    </select-searchable>
</ion-item>
```
3. Prepare your component file for `SelectSearchable`.
```
import { Component } from '@angular/core';
import { SelectSearchable } from 'ionic-select-searchable';

class Port {
    public id: number;
    public name: string;
}

@Component({
    ...
})
export class HomePage {
    ports: Port[];
    port: Port;

    constructor() {
        this.ports = [
            { id: 1, name: 'Tokai' },
            { id: 2, name: 'Vladivostok' },
            { id: 3, name: 'Navlakhi' }
        ];
    }

    portChange(event: { component: SelectSearchable, value: Port }) {
        console.log('port:', event.value);
    }
}
```

## API
Detailed API documentation and ways if usage can be found in [Wiki](../../wiki).

## Development
1. Install dependencies.  
`npm install`  
2. Start build.  
`gulp`  
