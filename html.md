# HTML

### Best Practices

##### Don't nest your divs more than necessary

If you are using Bootstrap, for example, you are likely to have a layout that looks something like this:
```
<div class="container">
  <div class="row">
    <div class="col-md-12">
      Hello world
    </div>
  </div>
</div>
```

Try to avoid adding any additional divs between the container, the row and the col. If you want to add behaviour, then add an additional class within an appropriate existing div.
