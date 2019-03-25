# Shopify Breadcrumbs Based on Menu Structure

You can find a full description of this snippet and why it's so ridiculously complex to achieve such a simple thing at https://raisedbyturtles.org/shopify-breadcrumbs-based-on-menu-structure

## Basic Install
1. Add the breadcrumb.liquid to your snippets for your theme. Shopify has a [video on how to do this](https://www.shopify.com/partners/blog/88186566-tips-for-using-snippets-in-your-shopify-theme) if your don't know.
2. Link to the snippet in the templates for your products, collections, pages, etc. So, for example, in /theme/templates/product.liquid, you would add this where you want your breadcrumbs to appear:

    {% include 'breadcrumb' %}
3. Set up your [dropdown menus](https://help.shopify.com/en/manual/sell-online/online-store/menus-and-links/drop-down-menus)

That's it.

## Why does this code look so awful?
Perhaps it's just a function of my skill, but Shopify Liquid is a templating tool, not a programming language. It lacks basic data structures, has no function calls, can't do recursion. So you end up with this mess to do a simple thing.

## How does it work?
The basic idea here is that you use a set of parallel, one-dimnesional arrays that all should have the same number of elements. If I know that the title I want is the fifth element of the titles array, then I know that its handle is the fifth element of the handles array. There's a lot of looping around doing lookups to translate from one array to the other. 

The code itself has extensive comments which, hopefully, are enough for non-coders to decipher.

See also my short post on [faking multi-dimensional arrays in Shopify Liquid](https://raisedbyturtles.org/shopify-associative-arrays) for the basic idea.
