# remram

Remarkable markdown.

### Comment Walker

```js
/* <!--{ eval(comments) }--> */ {
  const commentsWalker = document.createTreeWalker(
    document.body,
    NodeFilter.SHOW_COMMENT
  );
  while (commentsWalker.nextNode()) {
    const node = commentsWalker.currentNode;
    const text = node.textContent;
    if (text[0] === '{') {
      Function(text).call(node);
    }
  }
};
```
