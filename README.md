# ng-options
Usage of angular ng-options for all type of arrays and objects

## Array ['val1', 'val2']
###Code:
```
<input type="hidden" name="result" value="{{item.result}}" />
<select  ng-model="item.result" ng-options="option as option for option in ['1', '2']" ng-init="item.result=item.result ? item.result : '1'" class="form-control"></select>
```
###Generated Output:
```
<select ng-model="item.result" ng-options="option as option for option in ['1', '2']" ng-init="item.result=item.result ? item.result : '1'" class="form-control ng-pristine ng-valid">
	<option value="0" selected="selected">1</option>
	<option value="1">2</option>
</select>
```
*Note: As value of options are being generated based on index, so to save the the correct value use a hidden field*

## Array of Objects [{},{},{}]
###Code:
```
$scope.arrayObject = [{'id': 123, 'name': 'name123'},{'id': 456, 'name': 'name456'},{'id': 789, 'name': 'name789'}];
<select ng-model="selectModel" ng-options="i.id as i.name for i in arrayObject" ng-init="selectModel=arrayObject[0].id"></select>
 ```
 ###Generated Output:
 ```
<select ng-model="selectModel" ng-options="i.id as i.name for i in arrayObject" ng-init="selectModel=arrayObject[0].id" class="ng-pristine ng-valid">
    <option value="0" selected="selected">name123</option>
    <option value="1">name456</option>
    <option value="2">name789</option>
</select>
 
