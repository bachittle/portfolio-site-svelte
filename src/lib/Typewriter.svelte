<script>
  export let text = 'Bailey Chittle'; // single item to type
  export let texts = []; // array of elements to type
  export let eraseText = true;

  let typedText = '';
  const typeSpeed = 80;
  
  let textsIndex = 0;
  if (texts.length != 0) {
    text = texts[textsIndex]; // initialize text to first element, then change this on the eraseText reset.
  }
  
  function typeWriter() {
    if (typedText.length < text.length) {
      typedText += text.charAt(typedText.length);
      setTimeout(typeWriter, typeSpeed);
    } else if (eraseText) {
      setTimeout(() => {
        typedText = '';
        if (texts.length != 0) {
          textsIndex++;
          // reset textsIndex if at the end
          if (textsIndex >= texts.length) {
            textsIndex = 0;
          }
          text = texts[textsIndex];
        }
        setTimeout(typeWriter, 1000);
      }, 2000);
    }
  }
  setTimeout(typeWriter, typeSpeed);
  
  let animatedCaret = '';
  export const caretChar = '|';
  
  function animateCaret() {
    if (animatedCaret.length == 0) {
      animatedCaret = '|';
    } else { 
      animatedCaret = '';
    }
  }
  setInterval(animateCaret, 400);
</script>

{typedText}{animatedCaret}