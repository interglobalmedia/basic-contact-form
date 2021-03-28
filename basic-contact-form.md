<h1 class="capitalize">COMD2451 Web Design 1</h1>
<h2 class="sentence center">Creating a Basic Contact Form with HTML and CSS</h2>

---

<section class="section">
	<h2 class="sentence">So what is an HTML5 form element and what is it for?</h2>

An `HTML5 form element` is **used** to ***collect*** `user input`. Usually the `user input` is **sent** to a `server/backend` for ***processing***.

The `form element` is a **container** for ***different*** `types` of `input elements`, such as: `text fields`, `checkboxes`, `radio buttons`, `submit buttons`, etc.

</section>

---

<section class="section">
	<h2 class="sentence">The form element</h2>

The `HTML form element` is **used** to ***create*** an `HTML form` for `user input`:

```html5
<form action="submit.html"
	  id="userForm">
	<h1 id="main-contact-heading">Contact Info for Maria</h1>
	<fieldset>
		<label for="firstname">First Name:</label>
		<input type="text"
			   name="firstname"
			   id="firstname"
			   placeholder="First Name here"
			   required>
	</fieldset>
	<fieldset>
		<label for="lastname">Last Name:</label>
		<input type="text"
			   name="lastname"
			   id="lastname"
			   placeholder="Last Name here"
			   required>
	</fieldset>
	<fieldset>
		<label for="email">Email:</label>
		<input type="email"
			   name="email"
			   id="email"
			   placeholder="Email here"
			   pattern="[a-z0-9._%+-]+@[a-z)-9.-]+\.[a-z]{2,}$"
			   required>
	</fieldset>
	<fieldset>
		<legend>Submit Info:</legend>
		<button type="submit"
				form="userForm"
				id="btn"
				aria-label="Left Align">Submit
		</button>
	</fieldset>
</form>
```

</section>

---

<section class="section">
	<h2 class="sentence">The form element and the action attribute</h2>

In our ***opening*** `form tag`, we have an **attribute** called `action` which **contains** the `value` of `"submit.html"`. The `action attribute` s***pecifies*** where to **send** `form-data` when a `form` is **submitted**. In ***other words***, it **specifies** the `URL` that ***should process*** the `form submission`.

In ***our configuration***, **nothing** is actually **submitted** to our `submit.html` page. We would have to ***first send*** an `HTTP request` to a `backend server/database`, and then a `response` would be **sent back** after the `data` was ***saved*** to a `database`. Then the `data` would be ***rendered*** to the **page**. This would have to ***involve*** a `scripting language` like `JavaScript`, `PHP`, `Python`, `Java`, `C++`, `C#`, etc., and the ***existence*** of a `backend database`, in order for it to **be able** to **happen**. We ***don't have*** any of that here. We ***only have*** `HTML` and `CSS`, which simply **creates** a `static form` with ***no real*** `functionality`.

Therefore, ***actually sending*** `form data` is **not done** on a `client-side` ***only*** website. All the `action attribute` ***does*** for us is **send us** to a **static** `submit.html` page which ***contains*** `pre-created text content` inside an `h1 element`. In **order** to **make** the `form` **more dynamic** on the `client-side`, we **would have** to **introduce** some `JavaScript` into the ***picture***. This ***however***, is **beyond** the ***scope*** of this `course`.

But what DOES the `action attribute` actually do when a `backend server/database` is ***actually configured***? The `value` of the `action attribute` would be the `url` to the **page** where the `response data` from the `backend server/database` **should** be **rendered**.

</section>

---

<section class="section">
	<h2 class="sentence">Sending form data</h2>

An `HTML form` on a **web page** is just a ***convenient***, ***user-friendly*** way to **configure** an `HTTP request` to **send data** to a `server`. This ***enables*** the `user` to **provide information** to be ***delivered*** in the `HTTP request` to the `server/database`. That ***means*** we would **need** a `backend-server` ***configured*** and a `backend database` ***configured*** to **save** the `data`. There is ***no point*** in truly **setting up** a `form` as we have **set up** here ***without*** those two **included** in our `site` as well. To **learn more** about ***how*** `client-server architectures` **work**, **read** MDN's [Server-side website programming first steps](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps) module.

</section>

---

<section class="section">
	<h2 class="sentence">The HTML5 form element and the HTML5 input element</h2>

The HTML `<input> element` is the ***most used*** `form element`.

An `<input> element` can be **displayed** in ***many ways***, **depending** on the `type attribute`.

The ***following*** is a **list** of the ***various*** `HTML input element` **types**:

+ [`<input type="text">`](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_input_text): the ***default*** `value` of the `type attribute` is `"text"`. It ***defines*** a **single line** `text input field`. The ***default*** `width` of an `input text field` is `20 characters`.

+ [`<input type="radio">`](https://www.w3schools.com/html/html_form_input_types.asp): ***displays*** a `radio button` (for selecting one of many choices).

+ [`<input type="checkbox">`](https://www.w3schools.com/html/html_form_input_types.asp): ***displays*** a `checkbox` (for selecting zero or more of many choices).

+ [`<input type="submit">`](https://www.w3schools.com/html/html_form_input_types.asp): ***displays*** a `submit button` (for submitting the form).

+ [`<input type="button">`](https://www.w3schools.com/html/html_form_input_types.asp): ***displays*** a `clickable button`.

In ***our*** `form`, we are **using** the `type="text"`, and `type="email"`.

***Instead*** of an `input` with `type="submit"`, we will be **using** a `button element` with `type="submit"`.

</section>

---

<section class="section">
	<h2 class="sentence">The input type="text"</h2>

The `input type="text"` **simply means** that ***whatever*** `plain text` the `user` **types** in the `input field` with the `type="text"` would be ***sending*** `plain text data` to the `backend server/database`.

</section>

---

<section class="section">
	<h2 class="sentence">The input type="email"</h2>

The `input type="email"` is **used** for `input fields` that ***should contain*** an `email address`. By ***default***, in the `browser`, you can ***type*** the `email address` ***without including*** the `.com` (or whatever) extension, and the `form` will be ***submitted***.

***Usually*** the `front-end developer` **sets up** the `client-side form`, so we would ***also*** want to make sure as `web designers` to ***change*** this ***default behavior*** so that the `form` would ***not submit*** if the `.com` or whatever other **extension** the `email address` **would contain**, if it was ***not included*** in the `data` **typed** in the `input field` with `type="email"`. We could even ***place restrictions*** on the `input field` with `type="text"` if we ***wanted to***.

</section>

---

<section class="section">
	<h2 class="sentence">The button type="submit"</h2>

We are ***not*** actually using an `input element` with the `type "submit"` for our f`orm button`. We are **using** a `button element` with the `type="submit"`.

The [HTML button element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) ***represents*** a `clickable button`, **used** to ***submit*** `forms` or **anywhere** in an `HTML document` for ***accessible***, ***standard*** `button functionality`. This of course, would then ***also involve*** `JavaScript`.

By ***default***, the **styling** of the `button element` is ***determined*** by the ***individual*** `user-agent` (`browser`). It is ***only*** when we **modify** that styling **using** `CSS` that its `appearance` ***changes***.

We **use** `form-related attributes` in our `button element` ***within*** our `HTML form`. We **use** the `type attribute` with the **value** of `"submit"`, and the `form attribute` which ***associates*** the `button` with a ***particular*** `form`.

The `button element`'s `type attribute` with the **value** of `"submit"`, ***permits*** the `button element` to **submit** `form data` to the `backend server/database`. This is the ***default*** if the `type attribute` is ***not specified*** for `buttons` **associated** with a `form element`, or if the `attribute value` is ***empty*** or ***contains*** an `invalid value`.

The `form attribute` of the `button element` ***associates*** the `button` with its `"form owner"`. In ***other words***, with a ***particular*** `form`. The **value** of the `form attribute` ***must be*** the `id d` of a `form` within the ***same*** `HTML document` (`page`). If this `attribute` is ***not set***, the `<button>` is **associated with** its ***ancestor*** `<form> element`, if ***any***. The `button` might ***not*** be a `child` of a `form`, and therefore would ***not contain*** a `form ancestor`.

In the **case** of ***our*** `form`, our `button element` **contains** the `form attribute` **value** of `"userForm"`, because the `id` of the `form element` on the `contact.html` **page** (here it is the `index.html` **page**) is `"userForm"`.

</section>

---

<section class="section">
	<h2 class="sentence">The Form's input element and the required boolean attribute</h2>

The `input elements` of our` form` ***also contain*** an `attribute` called `required`. It does ***not contain*** a `value`. Only the `name` of the `attribute` is **used**. ***Such*** an `attribute` is called a `boolean` attribute. This ***means*** that it can ***only contain*** one of two `values`: `true` or `false`.

if the `required attribute` is ***specified*** (present), it **means** that the `user` ***must specify*** a `value` for the `input` ***before*** the `form` can be ***submitted***.

The `required attribute` can be **used** with the `input types` of `search`, `url`, `tel`, `email`, `password`, `date`, `month`, `week`, `time`, `datetime-local`, `number`, `checkbox`, `radio`, `file`, `<input> types` along with the `<select>` and `<textarea>` **form control elements**.

The `required attribute` ***cannot*** be **used** with `inputs` of `type "range"` or `"color"`, since ***both*** have `default values`. It ***also*** can't be used with `hidden inputs`, **since** a `user` **can't** be ***expected*** to **provide** a `value` for an `input field` they ***cannot see***.

---

<section class="section">
	<h2 class="sentence">Our form and client-side built-in HTML5 form validation</h2>

One of the ***most powerful*** and ***significant features*** of `HTML5 forms` is their `form controls`. And the `form controls` ***permit*** the (`powerful`) `ability` to ***validate*** most `user data` WITHOUT RELYING on `JavaScript`! This is ***done*** by **using** `validation attributes` on `form elements`. ***One*** of those `attributes` is the `required attribute`.

</section>

---

<section class="section">
	<h2 class="sentence">Our form and HTML5 form controls</h2>

[HTML5 form controls](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types) ***include*** some new(er) `input types` **introduced** in `HTML5` to ***allow*** `collection` of ***specific*** `types` of `data`.

***One*** of these `types` is the `input` of `type="email"`, which ***we use***, and another is the `input type` of `"tel"`, for ***example***.

</section>

---

<section class="section">
	<h2 class="sentence">Our form and the HTML5 pattern attribute for type="email"</h2>

The `input element`'s [pattern attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern) ***specifies*** a `regular expression` the `form`'s `input element`'s **value** should ***match***. The **presence** of the `pattern attribute` on an `input element` with `type="email"` would ***prevent*** the `form` from **being submitted** if a ***valid*** `email address` was ***not provided***. In ***other words***, the `email address'` **extension** would **have** to be ***provided*** as well.

***What*** are `regular expressions`? [Regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)  are **patterns used** to ***match*** `character combinations` in `strings`. In `HTML5 built-in form validation` (which ***means*** `form validation` ***without*** the **use** of `JavaScript`, only `HTML`), it is the **value** of a `form element`\'s input ( aka `form control`) `pattern attribute`. It ***specifies*** a `regular expression` that ***defines*** a **pattern** the `entered data` needs to ***follow***. Basically, the ***data entered*** in the `input field` **has** to ***match*** the **requirements** of the `regular expression`.

</section>

---

<section class="section">
	<h2 class="sentence">The pattern attribute value of our input element of type="email"</h2>

In ***our*** `form`\'s `input element` ***targeting*** `type="email"`, I **add** the ***following*** `regular expression`:

```html5
<input type="email"
	   name="email"
	   id="email"
	   placeholder="Email here"
	   pattern="[a-z0-9._%+-]+@[a-z)-9.-]+\.[a-z]{2,}$"
	   required>
```

**Setting** the `required boolean attribute` to ***all*** of a `form`\'s `input controls` ***ensures*** that `forms` containing ***empty*** `input fields` **cannot** be ***submitted***.

**Setting** a `pattern attribute` to a `form`\'s `input control` ***ensures*** that a `form input field`\'s `value` ***must match*** a ***particular pattern*** in order to be `"submittable"`.

</section>

---

<section class="section">
	<h2 class="sentence">Breaking down the email input's pattern attribute value</h2>

Our `form`'s `input control` of `type="email"` ***contains*** a `pattern attribute` with the **value** of a `regular expression`. It ***looks*** like the ***following***:

```html5
pattern="[a-z0-9._%+-]+@[a-z)-9.-]+\.[a-z]{2,}$"
```

***What*** does the **above** `regular expression` ***mean***? Let's **break** it **down** piece by piece. I **use** a `regular expression` **translating site** to ***do this*** called [regexr.com](https://regexr.com/).

What the **value** of our `pattern attribute` is ***basically following*** is the `email address structure` of `characters@characters.domain` ( `.domain` representing `.net`, `.com`, `.co`, `.nyc`, etc).

First let's **take** a **look** at `[a-z]` located within the ***first*** `square brackets` to the **left** of the `pattern attribute value`. This ***means*** that the `input field`\'s **value** should ***match*** a `character` in the **range** of `"a"` to `"z"`. It is `case sensitive`. It ***should*** be `lowercase`, just as the `characters` ***passed*** to the `value` of the `pattern attribute`.

The `[0-9]` that ***follows*** within the ***same*** `square brackets` means that the `input field`\'s **value** should ***match*** a `character` in the **range** of `"0"` to `"9"`. It ***has*** to be ***within*** the **range** of **numbers** `0-9`. ***Not*** any other `number representation`.

The `[._%+-]` that ***follows*** included within the ***same*** `square brackets` means that the `email address` can ***also contain*** the `.`, `_`, `%`, `+`, or `-` **characters** as well.

`[a-z0-9._%+-]` ***points*** to the ***first*** `characters` **part** of the `email address structure` that our `pattern attribute value` ***requires*** the `user` to ***follow***.

The `+` sign that follows `[a-z0-9._%+-]` is called a `regular expression quantifier`, and it **means** to ***match*** 1 or more of the ***preceding token*** (what is ***between*** the `square brackets`). It ***also means*** that `characters` ***must contain*** at least 1 character.

The `@` symbol ***represents*** the `@` symbol in an `email address`.

The ***next*** `square bracket`, `[a-z0-9.-]` ***means*** that the `characters` ***following*** the `@` symbol in the ***required*** `email address structure` can ***contain*** characters within the **range** of `"a"` to `"z"` and `"0"` to `"9"` exactly. It can ***also contain*** a `.` character or a `-` character.

The `+` that ***follows*** the `[a-z0-9.-]` **means** that `characters` that ***follow*** the `@` symbol **match** 1 or more of the ***preceding token*** (what is ***between*** the `square brackets`). It ***also means*** that `characters` ***must contain*** at least 1 character.

The `\` **escapes** the `.` character that ***follows***. It simply means a `dot text character` and ***not*** something else, which it ***would mean*** by ***default*** if **not escaped**. This ***represents*** the `dot` that ***precedes*** the `email address extension`. i.e., `com`, `net`, `co`, `nyc`, etc.

The `[a-z]` ***means*** that the **value** of the `input field` ***provided*** by the `user` should ***match*** any character within the `"a"` to `"z"` **range**.

The `{2}` is ***also*** a `quantifier`, and it ***means*** that the `extension` should ***natch*** 2 or more characters **represented** in the `[a-z]` **square brackets**.

`$` ***represents*** the **end** of the `email address`. It ***denotes*** the **end** of the `email address`.

</section>

---

<section class="section">
	<h2 class="sentence">Related Resources</h2>

+ [HTML Forms: w3schools](https://www.w3schools.com/html/html_forms.asp)

+ [HTML Form Elements: w3schools](https://www.w3schools.com/html/html_form_elements.asp)

+ [`<form>`: MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)

+ [<input>: The Input (Form Input) element: MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

+ [`<button>`: The Button element: MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)

+ [Validation | required=“true” / “false” | HTML form: stackoverflow](https://stackoverflow.com/questions/48651166/validation-required-true-false-html-form/48651305)

+ [regexr.com](https://regexr.com/)

</section>

---
