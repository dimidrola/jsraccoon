# Поиск всех соседних элементов (siblings)
В jQuery есть очень полезный метод `$.fn.siblings()`, который возращает все соседнии элементы относительно выбранного. 
```javascript
$('.element').siblings();
```

JavaScript не содержит нативных методов для извлечения всех соседних элементов из DOM дерева, поэтому для получения пободной функциональности нужно написать функцию:
```javascript
var _getSiblings = function(el) {
	return [].filter.call(el.parentNode.children, function(child) { //use {Array.prototype.filter.call...} instead. This is faster
	  return child !== el;
	});
};
```

Применяя метод массивов `Array.filter()` на все дочерние элементы родителя выбранного элемента, можно получить всю коллекцию соседних элементов относительно выбранного.
