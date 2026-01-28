---
layout: default
---

<!-- Text can be **bold**, _italic_, or ~~strikethrough~~. -->

<div id="codeOverlay" class="overlay" style="position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.7); z-index: 9999; display: flex; justify-content: center; align-items: center;">
  <div class="overlay-content" style="background-color: rgba(255, 255, 255, 0.9); padding: 40px; border-radius: 10px; text-align: center; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
    <h1>View Code</h1>
    <input type="text" id="codeInput" placeholder="Enter access code" />
    <button onclick="checkCode()">enter</button>
    <p id="errorMsg" style="color: red; display: none;">Incorrect code</p>
  </div>
</div>

<script>
const HASHED_SECRET_CODE = "dcdc240c9e0c71a200eec8cc118ae8dbd640ae3f79b8d41515d96462bc09bcc7"; 

async function checkCode() {
  const input = document.getElementById('codeInput').value;
  const errorMsg = document.getElementById('errorMsg');
  
  // Hash the input and compare with stored hash
  const inputHash = await hashPassword(input);
  
  if (inputHash === HASHED_SECRET_CODE) {
    // Correct code - redirect to main page
    window.location.href = './afjsinme.html';
  } else {
    // Incorrect code - show error
    errorMsg.style.display = 'block';
  }
}

// Hash function (SHA-256)
async function hashPassword(password) {
  const encoder = new TextEncoder();
  const data = encoder.encode(password);
  const hashBuffer = await crypto.subtle.digest('SHA-256', data);
  const hashArray = Array.from(new Uint8Array(hashBuffer));
  const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join('');
  return hashHex;
}

document.getElementById('codeInput').addEventListener('keypress', function(e) {
  if (e.key === 'Enter') {
    checkCode();
  }
});
</script>

<!-- ### [NAS - Mar 2024](./nas-page.html) <img src="/assets/img/internet.png" alt="NAS logo" width="20" style="vertical-align: middle; margin-left: 6px;">

Software that supports file sharing often comes with latency issues and tedious authentication and complicated navigation. -->


<!-- [Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
``` -->
