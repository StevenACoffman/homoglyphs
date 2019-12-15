<script>
	export let input="";
	export let useHomoglyphs=true;

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
		const alphabet = {
	    A: ['🅰️'],
	    B: ['🅱️️'],
	    C: [ '©️', '☪️', '🗜️' ],
	    D: ['↩️'],
	    E: ['🅴','📧'],
	    F: ['🎏'],
	    G: ['🅶','⛽️'],
	    H: ['🏩','♓️'],
	    I: ['💈','ℹ️'],
	    J: ['☔', '🎷', '🗾'],
	    K: ['🅺', '🎋'],
	    L: ['👢', '🕒'],
	    M: [ 'Ⓜ️', '♏️', '♍️', '〽' ],
	    N: ['🅽','📈'],
	    O: ['🅾️', '⭕️', '💍'],
	    P: ['🅿️'],
	    Q: ['🍳','🍭','♌','🇶','ℚ','℺'],
	    R: ['Ⓡ','®️'],
	    S: [ '💰', '⚡️' ],
	    T: ['🏋', '✝️'],
	    U: ['🐋', '⛎'],
	    V: ['✌️️', '♈️'],
	    W: ['👐','〰️'],
	    X: [ '❎', '❌', '✖️', '🙅' ],
	    Y: ['🌱', '🍸'],
	    Z: ['💤'],
	    '!': [ '❗️', '❕' ],
	    '?': [ '❓', '❔' ],
	    '#': ['#️⃣'],
	    '*': ['*️⃣'],
	    '+': ['➕'],
	    0: ['0️⃣'],
	    1: ['1️⃣'],
	    2: ['2️⃣'],
	    3: ['3️⃣'],
	    4: ['4️⃣'],
	    5: ['5️⃣'],
	    6: ['6️⃣'],
	    7: ['7️⃣'],
	    8: ['8️⃣'],
	    9: ['9️⃣']
	};
		if (input === undefined || input === "" ) {
		  return "Empty Input!"
		}
		if(useHomoglyphs) {
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
			} else {
			return input
				.toUpperCase()
		    .split("")
		    .map(item => {
		      if (alphabet.hasOwnProperty(item)) {
		        return alphabet[item][
		          Math.floor(Math.random() * alphabet[item].length)
		        ];
		      } else {
		        return item;
		      }
		    })
		    .join("");
			}
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<input bind:value={input} placeholder="enter some text">
<label>
	<input type=checkbox checked={useHomoglyphs}  bind:checked={useHomoglyphs}>
	Yes! Use homoglyphs instead of Emoji
</label>

<h1>{homoglyph(input, useHomoglyphs)}</h1>
