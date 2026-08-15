# Copy-Edit Log — Regression

Tracks copy-editing passes over this module's `.qmd` documents. Clear-cut
typos/grammar/spelling errors are corrected directly in the source. Items
that need an author decision are left in place but wrapped in
`<mark>...</mark>` so they show up highlighted in the rendered HTML.

## narrative.qmd — 2026-08-15

### Fixed directly (typos, spelling, grammar)

| Line | Issue | Fix |
|---|---|---|
| 30 | "Where th terms ... is the where the expected line interscepts ... (the predictor, and $\epsilon$..." — stray/duplicate words, a typo, and an unclosed parenthesis, all in one sentence | "Where the terms ... is where the expected line intersects ... (the predictor), and $\epsilon$..." |
| 54 | "is to be estimate" | "is to estimate" |
| 59 | "is to uses a methods called" | "is to use a method called" |
| 81 | "sum of squared distances distances" (duplicate word) | "sum of squared distances" |
| 101, 151, 188, 386 | "interscept(s)" throughout — not a word; the statistical term is "intercept" | "intercept" (also fixed the capitalized label "*Interscept*" at line 188, which should match `lm()`'s actual `(Intercept)` output) |
| 104–105 | `model_distance <- function( interscept, slope, X, Y )` and its use in the function body — same typo, in code. Confirmed every call site passes this argument positionally (never by name `interscept=`), so renaming the parameter doesn't change behavior anywhere. | renamed parameter and its use to `intercept` |
| 174 | "iteratively soom in this grid" | "zoom in this grid" |
| 208 | "to see if it well behaved" (missing "is") | "to see if it is well behaved" |
| 226 | "we've been able to estiamte a model" | "estimate a model" |
| 248 | "probability associated the value" (missing "with") | "probability associated with the value" |
| 273 | "looking up the are under the curve" | "the area under the curve" |
| 330 | "...reject the null hypothesis." (phrased as a question) | "...reject the null hypothesis?" |
| 373, 412, 455, 534 | "mresured in New York during the period of 1 May **2973** - 30 September **2973**" — same typo repeated in all 4 table captions; the built-in `airquality` dataset is from 1973, not 2973 | "measured ... 1 May 1973 - 30 September 1973" (all 4 fixed together) |
| 466 | "predeictor varible ... made up of a random variables" | "predictor variable ... made up of a random variable" |
| 502 | "An in fact, we must be very careful" | "And in fact, we must be very careful" |
| 506 | "amount of pedictor variables" | "predictor variables" |
| 522 | "where as those whose" | "whereas those whose" |

### Flagged for your review (highlighted with `<mark>` in the source)

| Line | Text | Why it's flagged |
|---|---|---|
| ~23 | "In that some of the underlying variation goes towards explaining the patterns in the data and the rest of the variation is *residual* (or left over)." | "In that" as a sentence opener doesn't read cleanly — possibly meant to refer back to the equation just above ("In that [equation]..."), but I wasn't sure enough to rewrite it. |
| ~522 | "those whose $\delta AIC > 5.0$ are to be rejected as being informative" | This reads backwards — a high ΔAIC should mean a model is rejected for **not** being informative (poorly supported relative to the best model), not rejected *for* being informative. Left as-is since I didn't want to silently flip the stated meaning of a stats claim; please confirm the intended wording (likely "rejected as **not** being informative" or "rejected as uninformative"). |
