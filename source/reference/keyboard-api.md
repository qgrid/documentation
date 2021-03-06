---
title: Keyboard API
group: Reference
order: 9
---

Use keyboard API to handle key presses when q-grid is in focus.

```typescript
@Component({
    template: `
       <q-grid [model]="gridModel"></q-grid>
    `
})
export class MyComponent implements AfterViewInit {
    gridModel = this.qgrid.model();

    constructor(private qgrid: Grid) {}

    ngAfterViewInit() {
        this.gridModel.keyboardChanged.on((e) => {
            const { codes, status } = e.state;
            if (status === 'down') {
                console.log(codes);
            }
        });
    }
}
```
