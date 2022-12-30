## sample code
```javascript
class AppDashboard extends HTMLElement {
    constructor() {
        super();
        console.log("AppDashboard created");
        const shadowRoot = this.attachShadow({mode: "open"});
    }

    connectedCallback() {
        console.log("AppDashboard inserted into DOM");
        // add event listeners (if necessary)

		const template = document.querySelector("#dashboard-template");
        this.shadowRoot.appendChild(template.content.cloneNode(true));
    }

    disconnectedCallback() {
        console.log("AppDashboard removed from DOM");
        // remove event listeners (that were added in connectedCallback())
    }
}

window.customElements.define("app-dashboard", AppDashboard);

// the following will duplicate the component
const element = document.createElement("app-dashboard"); // "AppDashboard created" will be logged
document.body.appendChild(element); // "AppDashboard inserted into DOM" will be logged
```
