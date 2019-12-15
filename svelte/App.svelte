<script>
	export let output = "Type Something!";

	function homoglyph(input) {
	  const homoglyphs = {
	    a: ["\u0430", "\u00e0", "\u00e1", "\u1ea1", "\u0105"],
	    c: ["\u0441", "\u0188", "\u010b"],
	    d: ["\u0501", "\u0257"],
	    e: ["\u0435", "\u1eb9", "\u0117", "\u0117", "\u00e9", "\u00e8"],
	    g: ["\u0121"],
	    h: ["\u04bb"],
	    i: ["\u0456", "\u00ed", "\u00ec", "\u00ef"],
	    j: ["\u0458", "\u029d"],
	    k: ["\u03ba"],
	    l: ["\u04cf", "\u1e37"],
	    n: ["\u0578"],
	    o: [
	      "\u043e",
	      "\u03bf",
	      "\u0585",
	      "\u022f",
	      "\u1ecd",
	      "\u1ecf",
	      "\u01a1",
	      "\u00f6",
	      "\u00f3",
	      "\u00f2"
	    ],
	    p: ["\u0440"],
	    q: ["\u0566"],
	    s: ["\u0282"],
	    u: ["\u03c5", "\u057d", "\u00fc", "\u00fa", "\u00f9"],
	    v: ["\u03bd", "\u0475"],
	    x: ["\u0445", "\u04b3"],
	    y: ["\u0443", "\u00fd"],
	    z: ["\u0290", "\u017c"]
	  };
		if (input === undefined || input === "" ) {
		return "Empty Input!"
		}
	  return input
	    .split("")
	    .map(item => {
	      if (homoglyphs.hasOwnProperty(item)) {
	        return homoglyphs[item][
	          Math.floor(Math.random() * homoglyphs[item].length)
	        ];
	      } else {
	        return item;
	      }
	    })
	    .join("");
	}

	function handleKeydown(event) {
		const text = event.target.value;
		output = homoglyph(event.target.value);
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<input on:keydown={handleKeydown}>

<h1>{output}</h1>
