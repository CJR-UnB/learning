# WAI ARIA

Accessible Rich Internet Applications

 JavaScript has traditionally had a reputation for being inaccessible to users of assistive technologies such as screen readers, but there are now ways to create dynamic web user interfaces that are accessible to a wide variety of users.

Since the HTML 4 specification doesn't provide built-in tags that semantically describe these kinds of widgets, developers typically resort to using generic elements such as <div> and <span>. While this results in a widget that looks like its desktop counterpart, there usually isn't enough semantic information in the markup to be usable by an assistive technology. Dynamic content on a web page can be particularly problematic for users who, for whatever reason, are unable to view the screen. Stock tickers, live twitter feed updates, progress indicators, and similar content modify the DOM in ways that an assistive technology (AT) may not be aware of. That's where ARIA comes in.

Search Engine
	Special Programs - Search Spiders (crow the web)
		Those dont interpret the web the same way as people, they look for link, keywords, headers, and other semantic tags that help describe the structure and meaning of the content
	Web Standards and Best Practices lead to best accessibility
	https://www.w3.org/WAI/
	Check contrast on you web (See your site in greyscale (desaturate)) -> Spur -> http://www.spurapp.com
	Dont set font size using explicit pixel size, use relative values
	Dont put text in your images
	Links/Buttons to adjusts font size can be usefull
	Make sure all img have alt atribute
	<table>
		<caption></caption> -> describe content of table
		<tr>
			<th scope="col"></th>
		</tr>
	</table>