# Using Liferay Util Body Bottom

The body bottom tag is not a self-closing tag. It lets you add additional HTML or scripts to the bottom of the `body` tag. content placed between the opening and closing of this tag is passed to the [body_bottom.jsp](https://github.com/liferay/liferay-portal/blob/7.2.x/portal-web/docroot/html/common/themes/body_bottom.jsp#L26-L31) and outputs in this JSP. 

This tag also has an optional `outputKey` attribute. If several portlets on the page include the same resource with this tag, you can specify the same `outputKey` value for each tag so the resource is only loaded once.

The example configuration below uses the `<liferay-util:body-bottom>` tag to include JavaScript provided by the portlet's bundle:

```jsp
<liferay-util:body-bottom outputKey="bodybottom" >
	<script 
  src="/o/my-liferay-util-portlet/js/my_custom_javascript_body_bottom.js" 
  type="text/javascript"></script>
</liferay-util:body-bottom>
```

Now you know how to use the `<liferay-util:body-bottom>` tag to include additional resources in the bottom of the page's body. 

## Related Topics

* [Using the Liferay Util HTML Body Top Tag](./liferay-util-body-top.md)
* [Using the Liferay Util HTML Top Tag](./liferay-util-html-top.md)
* [Using the Liferay UI Taglib](../liferay-ui-tag-library.md)