<div align="center">

# 🎵 AMLL TTML DataBase

**High-performance word-level lyric database for Apple Music-like Lyrics (AMLL)**

---

[ [简体中文](https://github.com/amll-dev/amll-ttml-db/blob/main/README.md) ] &nbsp;|&nbsp; [ [ **English** ](https://github.com/amll-dev/amll-ttml-db/blob/main/README-EN.md) ]

<br/>

### 🌟 AMLL Ecosystem

| Project | Type | Description |
| :--- | :---: | :--- |
| [**Apple Music-like Lyrics**](https://github.com/amll-dev/applemusic-like-lyrics) | Client | The main player application |
| [**AMLL TTML Tool**](https://github.com/amll-dev/amll-ttml-tool) | Editor | Current standard lyric editor |
| [**AMLL Editor**](https://github.com/amll-dev/amll-editor) | Editor | Next-Gen editor (WIP) |
| [**AMLL Page**](https://github.com/apoint123/amll-page) | Web | Web-based player |

### 📚 Key Documentation

[**Review Guidelines**](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/instruction.md) &nbsp;/&nbsp; [**TTML Specification**](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification.md)

</div>

<br/>

> [!TIP]
> ### 📣 Announcement
> **We are recruiting content reviewers and long-term maintainers!**
> <br>For more details, please visit the [Discussion Thread](https://github.com/amll-dev/amll-ttml-db/discussions/8127). Thank you for supporting this project!

> [!Warning]
> **Notice to Developers**
> <br>This repository has been migrated to the [amll-dev](https://github.com/amll-dev) organization.
> <br>New URL: **[https://github.com/amll-dev/amll-ttml-db](https://github.com/amll-dev/amll-ttml-db)**
> <br>Please update your downstream repositories accordingly.

> [!Important]
> **A note for non-Chinese contributors**
> <br>
> * **Language:** This database is primarily for Chinese speakers. If translating to other languages, strictly specify `xml:lang`.
> * **Preservation:** If a version already exists, please preserve it.
> * **Translation:** Since AMLL does not natively support multilingual toggles, use third-party tools (e.g., [ranhengzhang/ttml-trans-filter](https://github.com/ranhengzhang/ttml-trans-filter)) to filter languages before use.
>
> 👉 *Details: [TTML Specification (Section 5.3)](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification-en.md#53-multi-language-and-background-support)*

---

## 📥 Lyric Submission Workflow

### 1. Check for Duplicates

**Policy:** Submissions must include an ID from at least one of the following: **[Netease Cloud Music (NCM)](https://music.163.com)** (Primary), [Apple Music](https://music.apple.com), [QQ Music](https://y.qq.com), or [Spotify](https://open.spotify.com).

> [!Tip]
> We strictly quality-check lyrics against the **NCM ID**. If you are submitting a special version for another platform (with >1ms offset), please specify this clearly.

#### Search Options

| Method | Description |
| :--- | :--- |
| **A. AMLL Lyric Site** | **(Recommended)** Visit [Search Page](https://amlldb.bikonoo.com/search.html) > Enter Title > Click <kbd>Search</kbd>. |
| **B. Repository Search** | Get the Song ID (see [Metadata Guide](https://github.com/amll-dev/amll-ttml-tool/wiki/%E6%AD%8C%E8%AF%8D%E5%85%83%E6%95%B0%E6%8D%AE)) and search inside this repo. |
| **C. SearchInAMLLDB** | Visit [SearchInAMLLDB](https://steamfinder.github.io/search-in-amlldb) > <kbd>Update Database</kbd> > Search by Title. |

> [!NOTE]
> **Check Issues first!** If an Open Issue exists with the label `歌词制作占位` (Lyric Creation Placeholder), someone is already working on it.

### 2. Create Lyrics

Please refer to the [Review Guidelines](./instructions/instruction.md) for full details.

#### ✅ Critical Rules
* **No Metadata in Body:** Do not include credits (Composer, Lyricist) in the text. Use metadata fields.
* **No Empty Lines:** Use `End Time` tags to generate instrumental intervals.
* **Chronological Order:** Start times must not be later than End times.
* **Modifications:** State the reason and original PR when fixing existing lyrics.
* **Translations:** Use `<span ttm:role="x-translation">` or `<span ttm:role="x-roman">`.

#### 🛠️ Tools
We recommend the **[AMLL TTML Tool](https://amll-ttml-tool.stevexmh.net)** or **[AMLL Editor](https://editor.amll.dev)**.

**Quick Shortcuts for AMLL TTML Tool:**

| Key | Action | Description |
| :---: | :--- | :--- |
| <kbd>F</kbd> | **Start Time** | Sets the start of the current word. |
| <kbd>G</kbd> | **End + Next** | Sets End Time, moves to next word, sets next Start Time. |
| <kbd>H</kbd> | **End Only** | Sets End Time and moves to next (creates a gap/instrumental). |

### 3. Submit Lyrics

* **Via Issue (Recommended):** Use the [Submission Template](https://github.com/amll-dev/amll-ttml-db/issues/new?template=submit-lyric.yml).
* **Via Pull Request:** Ensure formatting is strictly correct to avoid bot errors.
* **Via Website:** Submit through the [Creator Center](https://amlldb.bikonoo.com/manage.html).

### 4. Review Process

Submissions are reviewed by the **AMLL TTML Lyric Review Team**.

> [!TIP]
> **Bot Commands (in PR comments):**
> * `/update {Link}` - Update lyric file (re-triggers review)
> * `/label {Label}` - Add a label
> * `/close {Reason}` - Close submission

---

## 🎧 Using the Database

### Clients
* **[AMLL Player](https://github.com/amll-dev/applemusic-like-lyrics/actions/workflows/build-player.yaml)**: Native client with local playback.
* **[AMLL Page](https://github.com/apoint123/amll-page)**: Web-based player.
* **[UniLyric](https://github.com/apoint123/Unilyric)**: Universal converter & SMTC broadcaster.

### Mirrors (for BetterNCM)
If the official source is unstable, add the following string in **Settings - Lyric Sources**:

**Steve-xmh Mirror:**
```text
61ba6770-f02f-11ef-a3ae-5396943709e6|AMLL%20TTML%20Database%20(Mirror)||ttml|[https://amll-ttml-db.stevexmh.net/ncm/](https://amll-ttml-db.stevexmh.net/ncm/)[NCM_ID]
```

---

## 🧩 Integration for Developers

We encourage developers to integrate this database. Attribution is appreciated.

**Directory Structure:**
* 📂 `ncm-lyrics/` (Netease Cloud Music)
* 📂 `qq-lyrics/` (QQ Music)
* 📂 `am-lyrics/` (Apple Music)
* 📂 `spotify-lyrics/` (Spotify)

**Available Formats:**
`.ttml` (Original), `.lrc`, `.yrc`, `.qrc`, `.lys`, `.eslrc`

---

## 📜 License & Credits

* **License:** External data follows original provider's license. Contributor content is **CC0 1.0**.
* **Community:** Join the discussion at QQ Group `719423243`.

[![Contributors](https://amll-ttml-db.stevexmh.net/contributors.png)](./CONTRIBUTORS.md)
