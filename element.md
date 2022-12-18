[element.textContent](textContent)
[element.innerHTML](innerHTML)
[element.value](value)

## classes
List of methods to dynamically add or remove classes **on** element.
1. `element.classList.add()`
2. `element.classList.remove()`
3. `element.classList.contains(className)` -> returns true or false
4. `element.classList.toggle(className)` -> ads or removes a class on element (depends on if it is present or not)
5. `element.classList.replace(oldClassName, newClassName)` -> one line method to remove old class and add new one
6.  `element.classList.add(firstClass, secondClass)` -> ads multiple classes at one time
7. `element.classList.remove()` -> removes multiple classes at one time

1. You can only access `.classList` on a single element. If you had a NodeList (from `document.querySelectorAll`), then you need to loop through it with forEach.
2. To be able to manage classes (in this case remove a class), you have to start by accessing `.classList`. A common mistake is to try and call ❌`element.remove()` or ❌`element.removeClass()` but these methods **do not exist**.
3. All the methods under `classList` expect a **class name**. So you should **not** prefix the class name with a dot. ❌`element.classList.remove(".highlighted")` would not work as expected here.

### examples

Switching between tabs
```js
export const deactivateAllTabs = () => {
    document.querySelectorAll(".tab").forEach(tab => {
        tab.classList.remove("active");
    });
    // OR, since only one tab can be active at a time: 
    // document.querySelector(".tab.active").classList.remove("active");
}

/**
 * @param {HTMLElement} tab
 */
export const activateClickedTab = tab => {
    tab.classList.add("active");
}

```
