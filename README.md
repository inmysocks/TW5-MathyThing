!TW5-MathyThing


a math plugin for TiddlyWiki5

Currently this plugin contains:

*The action-storecount widget
*The storecount widget
*The sumfield widget
*The sumfield2 widget
*The prodfield widget
*The prodfield2 widget
*The increment widget

---

''The action-storecount widget'' - an action widget with similar functionality to the count widget. It takes a filter and will count the number of matching tiddlers and, on a button press or other initiating event, store the output in the designated field. It was created by combining the action-setfield and count widgets.

Usage:

`<$action-storecount $filter=<<someFilter>> $tiddler=someTiddler $field=someField/>`

Since it is a modification of the action-setfield widget and I haven't modifed this part, you may be able to store the output at the given index of a data tiddler, but I haven't tested that yet.

---

''The storecount widget'' - a widget with similar functionality to the count widget. It takes a filter and will count the number of matching tiddlers and store the output in the designated field. It was created by modifying the sumfield widget below.

Usage:

`<$storecount $filter=<<someFilter>> $tiddler=someTiddler $field=someField/>`

Since it is a modification of the action-setfield widget and I haven't modifed this part, you may be able to store the output at the given index of a data tiddler, but I haven't tested that yet.

---


''The sumfield widget'' - a widget that was made by modifying the list widget. It takes a filter and a given field and sums together everything in that field in the filtered tiddlers.

Usage:

`<$sumfield filter=<<someFilter>> sumfield=sumField tiddler=storeTiddler storefield=storeField defaultvalue=defaultValue/>`

It will take each tiddler listed when using `<<someFilter>>` and take the value in sumField from each of the tiddlers and sum them, the result will be placed in the storeField of the tiddler storeTiddler. If there aren't any numbers to sum than it will display defaultValue.

tiddler defaults to `<<currentTiddler>>` and defaultValue defaults to 0 if they aren't given inputs.

If one of the fields contains a non-numeric value than it is ignored. This includes empty fields.

---


''The sumfield2 widget'' - a widget that was made by modifying the list widget. It takes a filter and a given field and sums together two fields in the filtered tiddlers and stores the value in a third field.

Usage:

`<$sumfield2 filter=<<someFilter>> sumfield=sumField sumfield2=sumField2 storefield=storeField defaultvalue=defaultValue/>`

It will take each tiddler listed when using `<<someFilter>>` and take the value in sumField to the value in sumField2 in each of the tiddlers and the result will be placed in the storeField of each tiddler. If there aren't any numbers to sum than it will display defaultValue.

tiddler defaults to `<<currentTiddler>>` and defaultValue defaults to 0 if they aren't given inputs.

If one of the fields contains a non-numeric value than it is ignored. This includes empty fields.

---


''The prodfield widget'' - a widget that was made by modifying the list widget. It takes a filter and a given field and takes the product of everything in that field in the filtered tiddlers.

Usage:

`<$prodfield filter=<<someFilter>> prodfield=prodField tiddler=storeTiddler storefield=storeField defaultvalue=defaultValue/>`

It will take each tiddler listed when using `<<someFilter>>` and take the value in prodField from each of the tiddlers and take their product, the result will be placed in the storeField of the tiddler storeTiddler. If there aren't any numbers to sum than it will display defaultValue. 

tiddler defaults to `<<currentTiddler>>` and defaultValue defaults to 0 if they aren't given inputs.

If one of the fields contains a non-numeric value than it is ignored. This includes empty fields.

---


''The prodfield2 widget'' - a widget that was made by modifying the list widget. It takes a filter and a given two fields takes the product of those fields in the filtered tiddlers, then stores the result in a third field in each tiddler.

Usage:

`<$prodfield2 filter=<<someFilter>> prodfield=prodField prodfield2=prodField2 storefield=storeField defaultvalue=defaultValue/>`

It will take each tiddler listed when using `<<someFilter>>` and multiply the values in prodField and prodField2 in each of the tiddlers and the result will be placed in the storeField of each tiddler. If there aren't any numbers to sum than it will display defaultValue. 

tiddler defaults to `<<currentTiddler>>` and defaultValue defaults to 0 if they aren't given inputs.

If one of the fields contains a non-numeric value than it is ignored. This includes empty fields.

---

''The increment widget'' - a widget that increments a value in a field by a given amount

Note: Both the field and the increment value have to be numeric and exist. If you specifiy an empty field, or a field with a non-numeric value, than the widget won't do anything.

Usage:

`<$action-increment $tiddler=someTiddler $field=fieldToIncrement $increment=incrementValue $length=zeroPadLength $prefix=outputPrefix $intial=initialValue/>`

*$tiddler defaults to `<<currentTiddler>>`
*$field defaults to make_sure_you_give_a_field_parameter
*$increment defaults to 1
*$length has no default, if no length is given than the output will have no zero padding
*$prefix has no default, if no prefix is given the output isn't given a prefix
*$initial defaults to 0

Note: the `$length` input specifies the minimum length, so if your `$length` is set to 1 and your stored value is 10 the `$length` input does nothing. The `$length` is also independent of the `$prefix`.

It will take the value of someField and replace it with the value someField+someIncrement

There is no requirement that someIncrement be positive or an integer.