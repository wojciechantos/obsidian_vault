Element is the most general base class from which all element objects (i.e. objects that represent elements) in a Document inherit. It only has methods and props common to all kinds of elements. More specific, classes inherit from Element.

So, in order to be able to use methods that are element specific, we need to describe the type of that element by type assertion, because element is a generic type. Here is an example:

```ts
const btn = document.querySelector<HTMLButtonElement>('.class-name')!;

btn.disabled = true; 
/* Without delcaring the HTMLButtonElement type, we would get an error on disabled method because it is not associated with the basic Element type. It is element specific, button specific in this case. */
```

Other syntax variant but less common is this:

```ts
const btn = document.querySelector('.selector')! as HTMLButtonElement;
```