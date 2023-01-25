# Form Validation
### Example of form
```
<form>
    <input type="text">
    <input type="textarea">
    <input type="checkbox">
    ...
    <input type="submit">
</form>
```
## Steps to Form Validation
### Step 1: Create a form in HTML with name attributes
```
<form name="formName">
    <input type="text" name="name">
    <button>Submit</button>
</form>
```
### Step 2: Bind Input with ng-model
```
<form name="formName">
    <input type="text"
           name="name"
           ng-model="ctrl.name">
    <button ng-click="ctrl.go()">Submit</button>
</form>
```
### Step 3: Declare HTML5 Validation Attributes
```
<form name="formName" novalidate>
    <input type="text"
           name="name"
           ng-model="ctrl.name"
           required
           min-length="4">
    <button ng-click="ctrl.go()">Submit</button>
</form>
```
### Step 4: Use Angular Form Bound Objects
```
<input type="text"
       name="name"
       ng-model="ctrl.name"
       required
       min-length="4">
<span ng-if="formName.name.$error.required && formName.name.$touched">
    Name is required
</span>
...
<button ng-disable="formName.$invalid"
        ng-click="ctrl.go()">
    Submit
</button>
```

### Step 5: Use Angular Validation Styles
```
.ng-touched.ng-valid{
    border: 2px green solid;
}

.ng-touched.ng-invalid{
    border: 2px red solid;
}
```