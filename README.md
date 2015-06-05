# cloning nodes

Il est pas possible d'insérer un node dans 2 endroits différents du DOM.

[Why isn't possible to append a same child in two dom element?](http://stackoverflow.com/questions/30667088/why-isnt-possible-to-append-a-same-child-in-two-dom-element)

Cela peut poser des problèmes, par exemple si l'on souhaite **fire** un event dans plusieurs parties du DOM en utilisant un seul élement logique.
La solution est donc de cloner l'élement avec une classe commune à tout ces mêmes élements et 
```javascript
[].forEach.call(document.querySelectorAll('.myClass'), function (e, i) {
	// e.g. -> e.fire('update');
	// Polymer's function
});
```