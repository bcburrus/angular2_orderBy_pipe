# angular2_orderBy_pipe
Generic Pipe for ordering Angular2 Array

To use:

app.module

    import { OrderByPipe } from './shared/orderBy.pipe'; <- replace with whereever you drop the pipe

    @NgModule({
        ...
      declarations: [ 
          ...
        OrderByPipe
        ]
        ...
    })

list.component.html

    <th><a (click)='onOrderBy("project_name")'>Name{{orderBy === 'project_name' ? orderDesc ? '▼' : '▲' : ''}}</a></th>

list.component.ts

    orderBy: string = 'project_name';
    orderDesc: boolean = false;

    ...

    onOrderBy(field: string): void {
        if (this.orderBy === field) {
            this.orderBy = field;
            this.orderDesc = !this.orderDesc;
            return;
        }
        this.orderBy = field;
        this.orderDesc = false;
    }
