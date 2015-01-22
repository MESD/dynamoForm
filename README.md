## DynamoForm.js

A jquery based dynamic form field generator with support for Select2.

![DynamoForm Example](https://github.com/MESD/DynamoForm/blob/master/demo/DynamoForm.png "DynamoForm Example")

**Status:** Beta (Jan 22, 2015)

**To Do:**
* Add prototype option for row creation (apoosed to copying last row)

## Usuage

### html layout:

Below is the needed html elements to turn your standard form into a dynamic
form.

``` html
<div class="dynamo-form">
    <div class="dynamo-form-row">
        <!-- your html form fields here -->
        <button type="button" class="dynamo-form-row-delete">Delete</button>
    </div>
    <button type="button" class="dynamo-form-row-add">Add</button>
</div>
```


### Example:

Here is a sample form for collecting multiple email addresses.

DynamoForm will automatically re-index the input id and name attributes each
time the user adds or removes a form row. It's important that the id and
name attributes end with a `_#` or `#]` for indexing to work. Where `#`
represents a positive integer.

``` html
<div class="dynamo-form">
    <div class="dynamo-form-row">
        <label>Email</label>
        <input type="text" id="user_email_1" name="user[email][1]" />
        <button type="button" class="dynamo-form-row-delete">Delete</button>
    </div>
    <button type="button" class="dynamo-form-row-add">Add Email</button>
</div>
```


### Example with advanced options:

You can limit the minimum and/or maximum number of addresses by specifying the
`data-min-rows` and/or `data-max-rows` attributes on the element with class
`dynamo-form`.

If you want Dynamo to re-index your field label text as well, add an
`data-dynamo-relabel="true"` attribute to your element holding the field label.
It's important that the field label text end with a `[space]#` for indexing to
work. Where `[space]` represents a space character and `#` represents a
positive integer.

``` html
<div class="dynamo-form" data-min-rows="1" data-max-rows="4">
    <div class="dynamo-form-row">
        <label data-dynamo-relabel="true">Email 1</label>
        <input type="text" id="user_email_1" name="user_email_1" />
        <button type="button" class="dynamo-form-row-delete">Delete</button>
    </div>
    <button type="button" class="dynamo-form-row-add">Add Email</button>
</div>
```


### Bootstrap Example:

Here is the same email address collection form using bootstrap based form code.

``` html
<div class="dynamo-form"  data-min-rows="1" data-max-rows="4">
  <div class="dynamo-form-row form-group">
    <label for="email_1"  class="col-md-3 control-label" data-dynamo-relabel="true">Email 1</label>
    <div class="col-md-6">
      <input type="email" class="form-control" id="email_1" placeholder="Enter email addresss">
    </div>
    <div class="col-md-1">
      <button type="button" class="btn btn-default dynamo-form-row-delete" disabled="disabled">Delete</button>
    </div>
  </div>
  <div class="col-md-offset-3 col-md-2">
    <button type="button" class="btn btn-default dynamo-form-row-add">Add Email</button>
  </div>
</div>
```
