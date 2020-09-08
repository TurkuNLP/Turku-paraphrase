# Annotation guidelines

## Changes (updated 26.6.2020)

Add rules for pronoun and time reference differences (25.6)
Add example for determiners (26.6)

## Basic scheme

For each pair of paraphrases, a number is assigned

- 4: The sentences are paraphrases in all non-absurd situations
- 3: The sentences can be paraphrases in some, but not all non-absurd situations
- 2: The sentences are related, but could hardly be paraphrases in non-absurd situations
- 1: There is no apparent link between the two sentences
- x: Although the two sentences may be paraphrases, they are not of interest for the purpose of corpus construction (e.g. spelling differences, `Mitä odotamme?` and `Mitä me odotimme?`)

## Flags

In addition to the numbers, there are optional flags that can be appended.

### The following flags can be appended to 4

- The subsumption flags: `>` or `<`, where the arrow points to the more general statement, i.e. the state that can be implied from the other statement. e.g. `Ei minua nukuta` and `En ole väsynyt`: `4>`; `Loistava ajoitus` and `Tulit juuri sopivasti`: `4<`.
- `R` for register: differentiates between book language, spoken language, and slang. Swear words. e.g. `20 taalaa vai ?` and `Kaksikymppiäkö ?`; `Helou gimmat` and `Päivää tytöt`/`Moi tytöt`. Note that minor differences such as `Loukussa ollaan .` and `Olemme ansassa .` are not taken into account. A general rule of thumb for distinguishing if a difference is markable is to imagine, when given one sentence, would the machine generating the other be desirable.
- `T` for tone: used when there is a markable difference in the strength of the statements. e.g. `tottakai` and `toki`. Minor differences are not counted (e.g. `Hei, rouvat` and `Päivää, naiset` are assigned `4` without the `T` flag). Similar to the criteria for marking `R`, a general rule of thumb for distinguishing if a difference is markable is to imagine, when given one sentence, would the machine generating the other be desirable. Hedging is marked with `T` e.g. `Se taitaa tarvita muutenkin lisää tilaa.` and `Se tarvitsee muutenkin lisää tilaa.`
- Bag-of-linguistic phenomena: `i`. The difference between `sinä` and `te` are always marked with `i` (not `T`). Second person passive are always marked with `i`. e.g. `Joskus amerikkalaisuus tarkoittaa, että pyydät anteeksi.` and  `Toisinaan amerikkalaisuus tarkoittaa anteeksipyyntöä.`

### The following flags can be appended to 3

- The `!` flag marks that the sentences are paraphrases in the given context, i.e. the label `4` entails this flag. e.g. `Antaudun .` and `Luovutan .`; `Ennen tätä .` and `Paitsi nyt .` Generally speaking, if the meaning of the two sentences have some overlap but neither one is a subset of the other, the label is `3!`.
- The label `3` without any flag entails that the two sentences could be paraphrases, but they are not in the given context.

## Secondary labels

- When the annotator feels that multiple tags may be appropriate, **use `|` to assign secondary labels**. e.g. `3!|4<t` Secondary labels are to be avoided when possible, and only used when alternative labels seem plausible.

## Rule of thumbs

- Focus on semantics instead of syntax.
- When both `4+` subsumption flags and `3!` is appropriate, `4+` subsumption takes precedence.
- When there is a conflict in the direction of arrows between parts of the sentence, use `3!`
- When the subsumption involves persons/numbers, use the `i` flag instead of the subsumption flags.
- Typo level differences are ignored (note to self: post-processing required when the corpus is used for generation)

## Rules for pronoun differences

- For true missing referent, assign subsumption e.g. `tämä tavara` vs. `tavara`, `Onko sinulla suihku?` and `Löytyykö suihkua?`
- For empty pronoun such as sinä passiivi, assign `i`
- Assign subsumption when there is a difference in the scope due to determiners such as `kaikki`. e.g. `Tein listan kaikesta pahasta, mitä ikinä olen tehnytkin. Yksi kerrallaan aion hyvittää kaikki virheeni.` and `Tein listan pahoista teoistani ja lähdin hyvittämään niitä.` are labelled `4>`

## Rule for time reference

- Assign subsumption when there is a difference in time reference but the tense is the same. Example keyword: `koskaan` e.g. `Oletko koskaan ollut verkossa?` and `Oletko käynyt netissä?`

## Example annotations

`Ne tekevät tepposet sinulle.`	`Ne huijaavat.` `4R>`
