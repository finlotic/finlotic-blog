# i18n Standards Part 1 <!-- omit in toc -->

[Blurb about why standards are important, how they're needed when people need to work together. Compare with standardization of [safety signs](https://en.wikipedia.org/wiki/ISO_3864), [road traffic lights](https://www.iso.org/standard/31003.html), [shoe sizes](https://www.iso.org/standard/71594.html) and even [wine glasses](https://www.iso.org/standard/9002.html)! But also stress why standards are important, maybe a motivating example.]

There are hundreds of international standards-setting bodies, but the largest one is the International Organization for Standards (ISO), an international body with representatives from over 160 national standards organizations. They develop voluntary international standards covering a broad range of topics, including manufacturing processes, food safety, software and healthcare.

Other standards-setting bodies relevant for software engineers include the Internet Engineering Task Force (IETF), the World Wide Web Consortium (W3C) and the Unicode Consortium, among others.

This post discusses some widely-accepted standards that are relevant to the internationalization (i18n) of software. Specifically, we'll talk about the following standards:

## Contents <!-- omit in toc -->

- [ISO 639: Language codes](#iso-639-language-codes)
  - [ISO 639-1: 2-letter codes](#iso-639-1-2-letter-codes)
  - [ISO 639-2, ISO 639-3: 3-letter codes](#iso-639-2-iso-639-3-3-letter-codes)
- [ISO 3166: Country codes](#iso-3166-country-codes)
- [ISO 4217: Currency codes](#iso-4217-currency-codes)
- [ISO 15924: Script codes](#iso-15924-script-codes)
- [BCP 47: Locale identifiers](#bcp-47-locale-identifiers)
- [Notes about using these standards](#notes-about-using-these-standards)
  - [Changes to standards](#changes-to-standards)
  - [Tagalog vs. Filipino?](#tagalog-vs-filipino)
  - [Chinese: Simplified vs. Traditional](#chinese-simplified-vs-traditional)
  - [Languages and Scripts](#languages-and-scripts)
    - [Chinese (`zh`)](#chinese-zh)
    - [Serbian (`sr`)](#serbian-sr)
    - [Azerbaijani (`az`)](#azerbaijani-az)
    - [Kazakh (`kk`) and Mongolian (`mn`)](#kazakh-kk-and-mongolian-mn)
    - [Mongolian (`mn`)](#mongolian-mn)
- [Conclusion](#conclusion)

This post won't dive into the Unicode standards — we'll cover them in excruciating detail in another post!

## ISO 639: Language codes

ISO 639 assigns 2-letter and 3-letter codes to identify languages. All codes are preferably expressed in _lowercase letters_.

The standard consists of several parts:

- ISO 639-1: 2-letter codes
- ISO 639-2, ISO 639-3: 3-letter codes

### ISO 639-1: 2-letter codes

For example:

| : ISO 639-1 code : | : Language : |
| ------------------ | ------------ |
| `en`               | English      |
| `fr`               | French       |
| `de`               | German       |
| `ta`               | Tamil        |
| ------------------ | ------------ |

This list is rarely expanded, especially since there is a finite number of two-letter codes. Out of the 676 possible two-letter codes, 184 have been assigned to a language in this standard.

The languages with 2-letter codes in this list are typically modern and highly-spoken languages. There _are_ exceptions — for instance, `ae` represents _Avestan_ or _Zend_, and `sa` represents _Sanskrit_, both of which are considered "ancient" languages.

Here's a complete list of ISO 639-1 language codes: https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes

### ISO 639-2, ISO 639-3: 3-letter codes

2-letter codes can only represent up to 676 languages. Clearly, not every language in the world can be represented.

Hence, the standard provides 3-letter codes to describe an even wider set of languages, including historical and ancient languages. (With 3-letters, up to 17,576 languages can be represented.) The standard also lists "macrolanguages" and language families in addition to international languages.

Although languages with a 2-letter code also have a corresponding 3-letter code, the 2-letter code is preferred in most contexts. Here are some examples of 3-letter codes:

| : ISO 639-2/3 code : | : Language : |
| -------------------- | ------------ |
| `eng`                | English      |
| `deu/ger`            | German       |
| `haw`                | Hawaiian     |
| `kok`                | Konkani      |
| ------------------   | ------------ |

An interesting aspect of the standard is that it intentionally reserves codes in the range `qaa - qtz` for "private-use". For instance, the [_Na'vi_ language](https://en.wikipedia.org/wiki/Na'vi_language) from the movie [_Avatar_](<https://en.wikipedia.org/wiki/Avatar_(2009_film)>) doesn't have an ISO 639 code. However, if two parties agree to interpret the code `qnv` as representing _Na'vi_, then they can freely use that code without worrying that the code may also represent some other real-life language.

Here's a complete list of ISO 639-2 codes: https://en.wikipedia.org/wiki/List_of_ISO_639-2_codes
And a list of ISO 639-3 codes: https://en.wikipedia.org/wiki/List_of_ISO_639-3_codes

## ISO 3166: Country codes

ISO 3166 defines 2-letter and 3-letter codes to represent countries, territories and geographical areas of the world. The codes are preferably represented using _UPPERCASE LETTERS_, and in general, the 2-letter codes are preferred.

The standard consists of two parts:

- ISO 3166-1: 2-letter and 3-letter country codes
- ISO 3166-2: Codes for provinces and regions

Here are some examples of codes:

| : ISO 3166 code :  | : Country/Province : |
| ------------------ | -------------------- |
| `US`               | USA                  |
| `DE`               | Germany              |
| `FR`               | France               |
| `IN`               | India                |
| `US-CA`            | California, USA      |
| `IN-KA`            | Karnataka, India     |
| `GB-ENG`           | England, United      |
| `IR-10`            | Khūzestān, Iran      |
| ------------------ | -------------------- |

As you might imagine, deciding what counts as a country [can be dicey and politically charged](https://www.youtube.com/watch?v=4AivEQmfPpk&list=PL89cWkYpvewDH1iltsyvJ_EU3CaQXRQHp). Hence, this standard is full of quirks. For instance:

- _Puerto Rico_ is unambiguously part of the USA but has its own code `PR`. Other non-independent regions with 2-letter codes include Bermuda (`BM`), the _British Indian Ocean Territory_ (`IO`).
- _Antarctica_ is not a country, but has code `AQ`. There's also a _French Antarctica_ (`FQ`).
- The United Kingdom has code `GB`, which stands for "_Great Britain_". _Great Britain_ is only the name for the largest island of the UK, and doesn't include Northern Ireland. Interestingly, the code `UK` is "reserved" to prevent it from being assigned to any country (and cause confusion with the United Kingdom).
- _Hong Kong_ (`HK`), _Taiwan_ (`TW`) and _Macau_ (`MO`) have complex histories with China. China has also specified regional ISO 3166-2 codes `CN-HK`, `CN-TW` and `CN-MO` for these areas respectively.

Like ISO 639, the ISO 3166 standard provides ranges of reserved 2-letter codes for "private use": `AA`, `QM - QZ`, `XA - XZ` and `ZZ`. For instance, the code `XK` is commonly used to identify _Kosovo_, a partially-recognized country that is considered by some to be an autonomous region in Serbia.

Fun fact: The Internet Corporation for Assigned Names and Numbers (ICANN) used ISO 3166-1 codes to determine _internationalized country code top-level domains_. For instance, a website with domain name `company-name.de` possibly has ties with Germany, and `company-name.in` possibly has ties with India.

## ISO 4217: Currency codes

ISO 4217 lists 3-letter codes to indicate currency units. Here are some exmaples:

| : ISO 4217 code :  | : Currency :         |
| ------------------ | -------------------- |
| `USD`              | US Dollar            |
| `GBP`              | Pound Sterling (UK)  |
| `JPY`              | Japanese Yen         |
| `EUR`              | Euro                 |
| ------------------ | -------------------- |

Typically, the first two letters of the currency code is an ISO 3166-1 code representing the country that uses the currency, while the third letter represents the English name of the currency. Of course, there are exceptions. For instance, `EUR` doesn't match the pattern (although `EU` is a "reserved" ISO 3166-1 code).

The standard also specifies that currencies beginning with the letter 'X' are "supranational" currencies that are not associated with any single nation. For example, `XAU` (gold), `XAG` (silver), `XPT` (platinum) and `XXX` (transactions that don't involve currency).

Unlike the ISO 639 and ISO 3166, ISO 4217 does _not_ designate ranges of code for "private use". This has the unfortunate consequence that various unofficial and unstandardized currencies such as cryptocurrencies cannot be easily represented. _Bitcoin_ is often unofficially coded as `BTC`, but this conflicts with the standard: Is `BTC` a currency of _Bhutan_ (with ISO 3166 code `BT`)? Similarly, the unofficial code for _Ethereum_ `ETH` could be incorrectly associated with _Ethiopia_ (`ET`).

## ISO 15924: Script codes

ISO 15924 defines 4-letter codes and numeric codes to identify written _scripts_ or writing systems. The codes are typically written in _Sentence case_ (only the first letter of the code is capitalized).

Here are some examples of common scripts:

| : ISO 15924 code : | : Script :                                                   |
| ------------------ | ------------------------------------------------------------ |
| `Latn`             | Latin (Latin script for English, French, German, etc.)       |
| `Cyrl`             | Кирилл (Cyrillic script for Russian, etc.)                   |
| `Deva`             | देवनागरी (Devanagari script for Hindi)                       |
| `Arab`             | عربية (Arabic script)                                        |
| `Taml`             | தமிழ் (Tamil script)                                         |
| `Brai`             | ⠃⠗⠇ (Braille script)                                         |
| ------------------ | ------------------------------------------------------------ |

Notice how the script names are derived from ISO 639 language codes where possible (like _Tamil_ (`ta`), _Arabic_ (`ar`)).

ISO 15924 also lists variants of scripts. For instance, `Latn` (Latin) has variants `Latf` (𝔉𝔯𝔞𝔨𝔱𝔲𝔯, Fraktur) and `Latg` (Gaelic); `syrc` (Syriac) has variants `Syre` (Estrangelo Syriac), `Syrj` (Western Syriac) and `Syrm` (Eastern Syriac).

Like all "good" standards, ISO 15924 also reserves ranges `Qaaa - Qabx` for "private use". It also specifies a number of special codes, including `Zyse` (emoji), `Zmth` (math notation), `Zxxx` (unwritten language).

## BCP 47: Locale identifiers

BCP 47 describes the construction of language tags or "locale" identifiers. This is the only non-ISO standard in this post — BCP (which stands for _Best Current Practice_) is an Internet Engineering Task Force (IETF) standard.

The full definition for a BCP 47 language tag can be found on [Wikipedia](https://en.wikipedia.org/wiki/IETF_language_tag#Syntax_of_language_tags), but at it's most basic, it consists of several tags separated by hyphens: An ISO 639 language tag followed by an optional ISO 15924 script tag and an optional ISO 3166 region tag.

Here are some examples:

| : BCP 47 language tag : | : Description :                                                       |
| ----------------------- | --------------------------------------------------------------------- |
| `en`                    | English                                                               |
| `en-US`                 | English, as spoken in the USA                                         |
| `en-GB`                 | English, as spoken in the United Kingdom                              |
| `haw-US`                | Hawaiian, as spoken in the USA                                        |
| `zh-Hans-CN`            | Chinese, written in the Simplified Chinese script, as spoken in China |
| ------------------      | ------------------------------------------------------------          |

## Notes about using these standards

I covered some of the quirks in each of the standards discussed above. However, there are some other quirks that result from changing cultural or political landscapes that affect the way software systems should work.

### Changes to standards

Countries come and go, the cultural landscape shifts and the names of currencies change. The standards listed in this post, especially ISO 639, ISO 3166 and ISO 4217, are not static — they are periodically updated based on requests of national standards organizations and governments.

Software engineers often write code that interacts with other systems that may be using older versions of these standards. When standards change, it's a good idea for software to support using both old and new versions of the standards where possible.

For instance, historically, Hebrew was represented by the ISO 639-1 code `iw`, probably in reference to the Hebrew name of the language "_Ivrit_". The code was later changed to `he`. However, some legacy software systems still use `iw` to refer to Hebrew. Other changes to language codes from ISO 639-1 include Indonesian (`in` became `id`) and Yiddish (`ji` became `yi`).

Similarly, _The Republic of Moldova_ started off with ISO 3166 code `MO`, but was changed to `MD`.

The Turkish Lira is the official currency of Turkey. It started off with ISO 4217 code `TRL` since `TR` represents _Turkey_ and `L` represents _Lira_. After decades of devaluation, the government decided to redenomiate the currency. In 2005, the "Yeni Türk lirası" ("New Turkish Lira") was introduced, and it was designated ISO 4217 code `TRY` (where `Y` refers to _Yeni_).

### Tagalog vs. Filipino?

Tagalog (`tl`) is a major regional language in the Philippines. In 1940, the Philippine government officially declared that Filipino (`fil`) would be the national language and that it was separate from Tagalog. However, Filipino is mutually intelligible with Tagalog — in fact, for most purposes, they are the same language! Software systems can usually treat `tl` and `fil` as equivalent.

### Chinese: Simplified vs. Traditional

Chinese (`zh`) and Japanese (`jp`) use the _Han script_, which is a combination of Hanzi, Kanji and Hanja (old Korean alphabet). The _Han script_ is represented by ISO 15924 code `Hani` (where `i` stands for _ideographs_).

There are two main variants of the `Hani` script: `Hant` (Traditionl Chinese) and `Hans` (Simplified Chinese). `Hant` is the older script, and is still used in Taiwan (Republic of China), Hong Kong and Macau. `Hans` was introduced the People's Republic of China in the 1950's, and is also used in Singapore and Malaysia.

Before BCP 47, many software systems used language tags that did not include a script tag. Instead, they used `zh-CN` to refer to Simplified Chinese, and `zh-TW` to refer to Traditional Chinese. However, this is inconsistent and problematic: What script should we use when the language tag is `zh-US` (Chinese as spoken in the USA)? In fact, it isn't _illegal_ to use Simplified Chinese in China, or Traditional Chinese in Taiwan.

Modern software systems should use the optional script subtag to differentiate between the two variants of Chinese: `zh-Hans` for Simplified Chinese, and `zh-Hant` for Traditional Chinese. (The optional region subtag can be added if needed, for instance, `zh-Hans-TW` for Simplified Chinese as used in Taiwan.)

### Languages and Scripts

As we saw in the discussion for [ISO 15924](#iso-15924-script-codes), a single script can be used to write in multiple languages. For instance, the Latin script (`Latn`) is used as the basis for most writing systems in the world, including Romance languages (English, French, etc.), among others.

Interestingly, the reverse is also possible: A single language can potentially be written using different scipts! Here are some examples.

#### Chinese (`zh`)

Dee [Chinese: Simple vs. Traditional](#chinese-simplified-vs-traditional)).

#### Serbian (`sr`)

Serbian (`sr`) is spoken in the countries Serbia (`SR`) and Montenegro (`ME`). Serbian is also written in either Cyrillic (`Cyrl`) or Latin (`Latn`). Although the official script used by the Serbian government is Cyrillic, both scripts are widely used in the country.

[TODO: Include image of newspapers from Montenegro, showing Cyrillic and Latin scripts. https://www.loc.gov/rr/european/images/montengrin-newspapers-large.jpg]

BCP 47 language tags can be used to differentiate these different usages:

- `sr-Cyrl-RS`: Serbian, written in Cyrillic script, as spoken in Serbia
- `sr-Latn-RS`: Serbian, written in Latin script, as spoken in Serbia
- `sr-Latn-ME`: Serbian, written in Latin script, as spoken in Montenegro

Pro tip: If your software supports displaying translations for Cyrillic Serbian, it's actually possible to programmatically transliterate the text into Latin Serbian! The Wikipedia page for the [_Scientific transliteration of Cyrillic_](https://en.wikipedia.org/wiki/Scientific_transliteration_of_Cyrillic) provides the rules for transliteration.

#### Azerbaijani (`az`)

The language Azerbaijani (`az`) is spoken in the country Azerbaijan (`AZ`) and in Iran (`IR`), among other places. Azerbaijani was traditionally written using the Arabic script (`Arab`). However, the Azerbaijani government started using the Cyrillic script (`Cyrl`) in the 1930s, and then transitioned to the Latin script (`Latn`) in the 1990s. Adoption has been slow: Azerbaijani speakers in Iran mostly use the Arabic script (`az-Arab-IR`), Dagestan (a province in Russia) uses Cyrillic (`az-Cyrl-RU`), and Azerbaijan uses Latin (`az-Latn-AZ`). Oh, and some people in Azerbaijan use the Cyrillic script too (`az-Cyrl-AZ`). Does your head hurt yet?

#### Kazakh (`kk`) and Mongolian (`mn`)

Kazakh, spoken in Kazakhstan (`KZ`), has been transitioning from the Cyrillic script (`kk-Cyrl`) to the Latin script (`kk-Latn`). Notice that since Kazakh is predominantly spoken only in Kazakhstan, there's usually no need to include the country code.

#### Mongolian (`mn`)

Mongolian is currently written in the Cyrillic script (`Cyrl`), but the Mongolian government recently pledged to make all official documents available in the traditional Mongolian script (`Mong`) by 2025. Interestingly, the [Mongolian script](https://en.wikipedia.org/wiki/Mongolian_script) is written vertically!

## Conclusion

TODO
