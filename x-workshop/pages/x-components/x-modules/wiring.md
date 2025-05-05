## Wiring

<br/>
<div class="max-w-[90%]">

##### · Each module has its own wiring to **listen to events** emitted across all the app and **trigger actions** from the module itself.

##### · Multiple modules can listen to the **same event** and react to it.
##### · The wiring of the modules is fully **customizable** from within a client setup, so you can add, remove or expand listeners and actions of any module.
</div>

<br/>

### Wiring flow example

<br />

```mermaid {scale: 0.65}
sequenceDiagram
participant A as User
participant B as Main Modal
participant C as Wiring (Bus)
participant D as Search Box Module
participant F as History Queries Module
A->>B: Clicks on closing X
B->>C: Emits UserClickedCloseX
C->>B: Listens UserClickedCloseX
C->>D: Listens UserClickedCloseX
C->>F: Listens UserClickedCloseX
```

<!--
* Modal is closed
* Query is cleared
* HQ are cleared
-->