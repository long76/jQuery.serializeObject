[![Build Status](https://travis-ci.org/hongymagic/jQuery.serializeObject.png)](https://travis-ci.org/hongymagic/jQuery.serializeObject)

# What is it?

`$.serializeObject` is a variant of existing `$.serialize` method which, instead
of encoding form elements to string, converts form elements to a valid JSON
object which can be used in your JavaScript application.

# Why?

Whilst it isn't necessary in most cases, and by that I mean 99.99% kind of most,
there are times when we manipulate form data on client side. Personally I find
JSON much easier to work with than DOM or string manipulation.

# How do I use it?

Simply include the `jQuery.serializeObject.js` along with any `jQuery` instance
and use it like `$.serialize`.

If you have a `form` like the following:

	<form id="minutes">
		<input type="text" name="subject">
		<input type="text" name="minute-taker">
		<!-- ... -->
		<input type="checkbox" name="attendees" value="David" checked="checked">
		<input type="checkbox" name="attendees" value="Daniel" checked="checked">
		<input type="checkbox" name="attendees" value="Darwin" checked="checked">
	</form>

and wish to convert them to a JSON object:

	var minutes = $('form#minutes').serializeObject();

will return:

	{
		"subject": "",
		"minute-taker": "",
		"attendees": [
			"David",
			"Daniel",
			"Darwin"
		]
	}

## [Change log](https://github.com/long76/jQuery.serializeObject/blob/master/CHANGELOG.markdown).

## Known issues

- In rare cases, this won't work with old checkbox/hidden hack. See [this issue for more details](https://github.com/hongymagic/jQuery.serializeObject/issues/9).
