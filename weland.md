---
layout: page
title: weland
---
# Weland

Weland is a simple yet powerfull language to express decoupling intention. Its core predicate is of the form _hide_ Xs _except_ xs _from_ Ys _but-not-from_ ys.

## Named elements, scope and range

What we call a named element for Java is the declaration of one of the following elements : a package, a class, an interface, a constructor, a field or a method. A scope is defined by a named element e and refers to the set of every nodes in the tree formed by the contain-arcs and rooted by e. In the weland syntax, a named element can be prepended by _r:_ where r stands for root. For a given named element e range(e)=scope(e) and range(r:e) = {e}.

## Set Definition

* `<set_id>`=[possibly_rooted_named_element*]
* `<set_id>`=*union*([set_id*])

For convenience, there is an import clause of the form
_import_ [named_element]

[home page](index.md)
