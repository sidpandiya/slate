# Errors

<aside class="notice">
This error section is stored in a separate file in <code>includes/_errors.md</code>. Slate allows you to optionally separate out your docs into many files...just save them to the <code>includes</code> folder and add them to the top of your <code>index.md</code>'s frontmatter. Files are included in the order listed.
</aside>

The Sike API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid - usually because there wasn't enough text in the <code>text</code> field!.
401 | Unauthorized -- Your API key is wrong.
404 | Not Found -- The specified URL could not be found.
405 | Method Not Allowed -- You tried to access an invalid method.
500 | Internal Server Error -- We had a problem with our server. Try again later.
