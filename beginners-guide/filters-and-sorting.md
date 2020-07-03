---
description: >-
  The true power of TagViewer is shown in the filters and sorting that it is
  capable of.
---

# Filters and Sorting

## Filters

As stated in the previous page, when you add filters, only the media that matches the filters is shown in the File List. In the Filters menu, you'll see the tags, colors, and properties available to make filters. If there are too many and there's not enough space, you can search the tags, colors, or properties by clicking the search button \(the magnifying glass\) next to the section names.

{% hint style="info" %}
**Incoming changes:** In TagViewer 1.1 you will be able to collapse the sections.
{% endhint %}

For [boolean](https://en.wikipedia.org/wiki/Boolean_data_type) \(yes or no\) filter options, you'll see two buttons before the name instead of one. When you click the plus, the filter will require the value to be true, and vice versa for the minus.

After every property filter option, there is a checkbox. If you hover over it, you'll see the message, "Include items that have no value for this property?" Since by default no value is set for any properties \(and they can be unset as detailed in the previous page\), you can choose whether to include items where their value for that property isn't set \(nonexistent\).

Additionally, for [string](https://en.wikipedia.org/wiki/String_%28computer_science%29) filter options, you can choose to require case matching with the second checkbox. Case matching means that if you filter for "Foo", "foo" and "FOO" will not be considered matching. By default case matching is not required.

## Sorting

In addition to filters, you may want to change the ordering of the items in the File List. This is the purpose of sorting.

When you change the sorting method, your media number is automagically changed to keep the current media previous to the resort.

After selecting a sorting method \(a property and an ordering\), you can set a secondary sorting method. This method is used if the property being compared is the same between two items. It defaults to the title.

Theoretically, there could be tertiary sorting and beyond, but for the sake of simplicity, only two sorting methods are offered currently.

