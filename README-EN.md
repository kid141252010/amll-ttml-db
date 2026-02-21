<div align=center>

# **AMLL TTML DataBase**

This is the TTML word-level lyric database for Apple Music-like Lyrics, providing support for better lyric performance in AMLL.

**—— AMLL Ecosystem Works ——**

[Apple Music-like Lyrics](https://github.com/amll-dev/applemusic-like-lyrics)
/
[AMLL TTML Tool Word-Level Lyric Editor](https://github.com/amll-dev/amll-ttml-tool)
/
[AMLL Editor Next-Generation Word-Level Lyric Editor](https://github.com/amll-dev/amll-editor) (In Development)
/
[AMLL Page Web Player](https://github.com/apoint123/amll-page)

**—— Important Documents in this Repository ——**

[Review Guidelines](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/instruction.md)
/
[TTML File Specification](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification.md)

</div>

***

> [!TIP]
>
> ## 📣 [Announcement]
> We are recruiting content review volunteers and long-term maintenance developers!  
> For more information, please check the [Announcement Post](https://github.com/amll-dev/amll-ttml-db/discussions/8127).  
> Thank you to all contributors for supporting this project!

***

> [!Warning]
> To developers using the lyric database:  
> This repository has been migrated to the [amll-dev](https://github.com/amll-dev) organization, and the repository link has been updated to https://github.com/amll-dev/amll-ttml-db. Please note the update for downstream repositories.

***

> [!Important]
>
> A note for non-Chinese contributors:
>
> This database is mainly for Chinese speakers. However, if you're translating lyrics into other languages, please specify it using the "xml:lang" attribute. If Chinese (or other language) version already exists, just keep all.
>
> Since AMLL series software currently does not support multilingual translations, users should get single-language-translated lyric by third-party tools (e.g. [ranhengzhang/ttml-trans-filter](https://github.com/ranhengzhang/ttml-trans-filter)) before using.
>
> Looking for more details? 👉[TTML Specification (Section 5.3)](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/ttml-specification-en.md#53-multi-language-and-background-support).
>
> ---
>
> *For demonstration purposes, the examples provided below are formatted. Please note that in an actual TTML file, the content is minified according to HTML standards. Keep this in mind when reading the examples and submitting files.*
>
> ---
>
> ###### Format 1:
>
> > **Example Code:**
> >
> > ```xml
> > <p begin="00:21.400" end="00:23.870" ttm:agent="v1" itunes:key="L1">
> >   <span begin="00:21.400" end="00:22.010">Low</span>
> >   <span begin="00:22.200" end="00:23.010">er</span>
> >   <span begin="00:23.010" end="00:23.210">Be</span>
> >   <span begin="00:23.210" end="00:23.870">ings</span>
> >   <span ttm:role="x-translation" xml:lang="en-US">Lower beings</span>
> >   <span ttm:role="x-translation" xml:lang="ja-JP">劣等な生物たちよ</span>
> > </p>
> > ```
> >
> > **Example File:**
> >
> > [HOYOMiX/YMIR - Flare](https://github.com/amll-dev/amll-ttml-db/blob/main/raw-lyrics/1752080938784-68000793-8355bb14.ttml)
>
> ---
>
> ###### Format 2:
>
> > **Example Code:**
> >
> > ```xml
> > <iTunesMetadata xmlns="[http://music.apple.com/lyric-ttml-internal](http://music.apple.com/lyric-ttml-internal)">
> >   <translations>
> >     <translation type="subtitle" xml:lang="zh-Hans">
> >       <text for="L1">Dawn has not arrived</text>
> >     </translation>
> >     <translation type="subtitle" xml:lang="el-GR">
> >       <text for="L1">Πριν απ' την αυγή</text>
> >     </translation>
> >   </translations>
> > </iTunesMetadata>
> > ```
> >
> > **Example File:**
> >
> > [Darren Korb - Time Belongs to Us](https://github.com/amll-dev/amll-ttml-db/blob/main/raw-lyrics/1762708573944-68000793-qnjnaX11.ttml)
> >
> > ---
> >
> > *Although this format complies with the new standards of Apple Music, we strongly discourage using it because most programs utilizing amll-ttml-db cannot parse it. Furthermore, if you submit lyrics in this format via the Issue, the bot will automatically convert them to the first format.*

***

# Lyric Submission Workflow

## 1. Check for Duplicate Submissions

In principle, the AMLL TTML DataBase primarily accepts lyrics with audio sources from [Netease Cloud Music](https://music.163.com), for the convenience of other users. We also accept lyrics with audio sources from [Apple Music](https://music.apple.com), [QQ Music](https://y.qq.com), and [Spotify](https://open.spotify.com). Therefore, the submitted TTML files should contain the ID of at least one of the four platforms mentioned above.

> [!Tip]
>
> During the review, we assume that the audio corresponding to all the IDs of all platforms listed in your submitted lyrics are identical, or the offset between the audio files is less than 1 ms. Therefore, for the lyric files in the database, we only provide word-level lyric quality assurance for the songs corresponding to the **valid** Netease Cloud Music platform IDs included in the file, **unless you have created and submitted a special version for the corresponding song on other platforms**.

> [!WARNING]
>
> Due to historical reasons, submissions before 2024 may contain some content that does not fully comply with current standards. Please understand! If you have concerns about these contents but have extra energy, you can consider submitting a contribution to correct them, and we will process them with priority!

### Search in the AMLL TTML Lyric Site for Submitted Lyrics (Recommended)

Please visit the [Search Interface](https://amlldb.bikonoo.com/search.html) of the AMLL TTML Lyric Site, enter the song name you want to submit lyrics for, and click the <kbd>Search</kbd> button. If there are no results, the song currently has no TTML lyrics, and your submission is welcome.

> Thanks to [@cybaka520](https://github.com/cybaka520) for building the lyric site!

### Search in this Repository for Submitted Lyrics

Please refer to the [Lyric Metadata Description](https://github.com/amll-dev/amll-ttml-tool/wiki/%E6%AD%8C%E8%AF%8D%E5%85%83%E6%95%B0%E6%8D%AE) to obtain the song ID of the lyrics you want to submit. Search for this ID within this repository. If there are no files, the song currently has no TTML lyrics, and your submission is welcome.

### Search in SearchInAMLLDB for Submitted Lyrics (Alternative)

Please visit [SearchInAMLLDB](https://steamfinder.github.io/search-in-amlldb), click the <kbd>Update Database</kbd> button at the very top to pull the data, enter the song name you want to submit lyrics for, and click the <kbd>Query</kbd> button. If there are no results, the song currently has no TTML lyrics, and your submission is welcome.

> Thanks to [@SteamFinder](https://github.com/SteamFinder) for building the search site!

### Check for Lyric Creation Placeholder Issues

If you are preparing to submit lyrics for a certain song, creating a **"Lyric Creation Placeholder"** Issue indicates that you have taken over the lyric submission work for that song, to avoid crashes caused by others submitting at the same time.

> [!WARNING]
>
> Contributors who publish a placeholder issue will have their submissions prioritized for review if they submit within 7 days of publishing the issue, regardless of whether anyone else has submitted the same contribution during this period.
>
> If it exceeds this time frame, we will still review them in the order of submission.
>
> The time frame is based on the **date displayed by the system when the placeholder issue was published** and the **date displayed by the system when the PR was automatically created**.
>
> If you have published a placeholder issue and submitted a contribution, we recommend referencing your issue in the remarks to reduce potential disputes.

Please visit the [Issues](https://github.com/amll-dev/amll-ttml-db/issues) section of this repository and search for the song name you want to submit lyrics for. If there are no Issues in an **Open status with the "Lyric Creation Placeholder" label**, then the lyric submission work for that song has not yet been taken over, and your submission is welcome.

You can also visit the [AMLL TTML Lyric Site](https://amlldb.bikonoo.com/) to search.

## 2. Create Lyrics

### Lyric Requirements

For the detailed lyric review rules, refer to [this file](./instructions/instruction.md). The following content is a brief overview of the basic requirements.

#### Hard Requirements

- Do not include information other than the lyric content in the lyric body, such as **Lyricist**, **Composer**, **Lyric Creator** information;
  > We recommend storing such information through the AMLL TTML Tool metadata function.
- Do not leave empty lines. Make good use of the **End Time** to allow the lyric player to automatically generate interlude areas;
- Word timing must not be incorrect, for example, the **Start Time** is later than the **End Time**;
- For English songs, the interval between words should not exceed one space;
- For correcting existing lyrics, please specify the reason for modification and the original PR in the supplementary description;
- Providing translated lyrics for songs involving political sensitivity or violating humanitarianism is prohibited (romanization is basically unrestricted). If it is a Mandarin song, lyric submissions will not be accepted.
  > For translations of lyric content that may have NSFW content, we do not object to expressing the original meaning, but please try to grasp the scale and stop at the appropriate point. Otherwise, the review may be delayed depending on the situation, or the lyrics may even be rejected.
  > 
  > *NSFW: Abbreviation for Not Safe For Work, meaning certain internet content is not suitable for browsing in the workplace. It is usually used to mark content containing nudity, violence, or pornography that is not suitable for viewing in a work environment.*
  
#### General Review Requirements

- Must be word-level lyrics, ensuring the timing difference is within ±100 milliseconds;
  > In principle, we still accept line-level lyrics. But unless there are special circumstances, we strongly prefer that you upload word-level lyrics to bring the best experience to the audience.
- Make full use of TTML lyric features, such as background vocal lyrics and duet lyrics;
- Provide translation and romanization (if any).
  > For lyric creators or lyric editor developers who do not use the AMLL TTML Tool, you can add `<span ttm:role="x-translation" xml:lang="...">...</span>` as translation text or `<span ttm:role="x-roman">...</span>` as romanization text in the `p` element of the line where you need to add romanization or translation.

> [!NOTE]
> You can use TTML lyric files from Apple Music, but generally, it is very difficult for such lyrics to be completely accurate. Please try to avoid submitting them directly without correction, to prevent being rejected by reviewers due to **excessive word offset values**.

### Use AMLL TTML Tool to Create Word-Level Lyrics

We recommend using the [AMLL TTML Tool](https://amll-ttml-tool.stevexmh.net) to create word-level lyrics. This README will briefly introduce the steps to use the AMLL TTML Tool.
> You can also use the [AMLL Editor](https://editor.amll.dev) developed by [@Linho1219](https://github.com/Linho1219) to create word-level lyrics. This editor introduces <kbd>Auto-scroll with playback</kbd> in the timing interface, as well as more practical functions.

You need to prepare:

1. A song audio file that can be read by the AMLL TTML Tool;
   > Formats protected by encryption are not supported.
2. A lyric file or plain text lyrics that can be recognized by the AMLL TTML Tool.
   > Supported lyric formats by AMLL TTML Tool: TTML / LRC / ESLyric / YRC / QRC / Lyricify Syllable

Then:

1. Click <kbd>File</kbd> and then <kbd>Import Lyrics</kbd> in the upper left corner, select the format of your imported lyrics, and import the lyrics according to the page prompts;
2. Import your song audio file in the lower left corner, adjust the playback speed and volume;
3. Click <kbd>Edit</kbd> and then <kbd>Edit Lyric Metadata</kbd> in the upper left corner, and edit the lyric metadata with reference to the [Lyric Metadata Description](https://github.com/amll-dev/amll-ttml-db/blob/main/instructions/instruction.md#1-%E5%85%83%E6%95%B0%E6%8D%AE);
4. Edit your lyrics in the **Edit** interface, such as word segmentation for lyric lines, changing lyric line attributes, filling in translation and romanization lyrics, etc.;
5. Create word-level lyrics in the **Timing** interface, play the audio, and make good use of the following keys to start timing:
   | Key | Description |
   | ------------ | ------------------------------------------------------------ |
   | <kbd>F</kbd> | Record the **current playback progress** as the **Start Time** of the current word. |
   | <kbd>G</kbd> | Record the **current playback progress** as the **End Time** of the current word, move to the next word at the same time, and record the **current playback progress** as the **Start Time** of that word. |
   | <kbd>H</kbd> | Record the **current playback progress** as the **End Time** of the current word, and then move to the next word.<br/>Usually used for the word ending the current sentence, leaving the interlude area empty, or presenting the singer's pausing singing style. |
6. After completing the timing, preview the word-level lyrics you made in the **Preview** interface;
7. After confirming the preview is correct, click <kbd>File</kbd> and then <kbd>Save TTML Lyric File</kbd> in the upper left corner to save the TTML lyric file.

## 3. Submit Lyrics

- We recommend submitting lyrics by [Creating a 'Submit/Correct Lyrics' Issue](https://github.com/amll-dev/amll-ttml-db/issues/new?template=submit-lyric.yml). You can view the detailed submission process on that page;

- You can also manually submit a Pull Request to submit lyrics. This requires you to ensure that your TTML lyric file is **correctly formatted**, and mimic the Pull Requests submitted by the Bot in this repository to write it;
   > This method can avoid formatting behaviors such as `Reordering Metadata` and `Reordering Lyric Lines by Timeline` performed by the Bot during lyric submission, but please make absolutely sure that the submitted TTML lyric file and Pull Request are **completely correctly formatted**.

- You can also submit lyrics in the [Creator Center](https://amlldb.bikonoo.com/manage.html) of the AMLL TTML Lyric Site. Uploading lyrics on the lyric site requires you to register and log in, click <kbd>Submit</kbd> and upload the TTML lyric file. Usually, the website will automatically recognize the lyric metadata and fill in the submission title; just submit it directly.
   > Currently, the lyric site has fewer reviewers. If you want a fast review, please prioritize submitting lyrics on GitHub.

> If your song does not have an available version on Netease Cloud Music, you can upload the song file yourself.
 > - In the Issue, you can fill in the song file download link in the Remarks section;
 > - In the Pull Request, you can fill in the song file download link in the `Remarks` / Comment in the Body;
 > - In the AMLL TTML Lyric Site Creator Center, you can click <kbd>Content Management</kbd>, find and click to enter the lyrics you want to upload the song file for, and then click <kbd>Upload Audio</kbd> to upload the song file.
 
## 4. Wait for Review

In order to improve the lyric consistency and comprehensive quality of the lyric database, your lyrics will be manually reviewed by the AMLL TTML Lyric Review Team to ensure that your lyrics meet the requirements of the [Lyric Review Guidelines](./instructions/instruction.md).

If your lyric submission is rejected, please modify the lyrics according to the reviewer's modification suggestions, and then try submitting again. The following are common reasons for rejection:

- Word timing error, or the offset value is too large;
- Over-correction:
  - Forcibly adding effects where they are not applicable to some effects;
  - Intentionally doing incorrect timing to trigger certain lyric effects.
- Lyric line attribute errors:
  - Did not correctly distinguish whether the current singer is in an auxiliary lead vocal state, or a solo duet singing state, so that background lyrics and duet lyrics were incorrectly set;
  - Unless the lyrics themselves do not consider using duet lyrics for the song, the correct duet lyrics should be set according to the primary and secondary relationship of the current singers. Without a clear motive, two different lyric states should not be set for the same singing form of the same singer.
    > **Singing form** can be lead vocal, rap, harmony, etc.

If you believe that your lyrics do not have the problems in the reviewer's modification suggestions, please try to submit again and attach the reason, so that the reviewer can understand your intention, or request other reviewers to review.
> [!TIP]
>
> If your lyric Pull Request is in an **Unreviewed** (no **Under Review** label) or **Review Failed** status, you can Comment in that PR `/update {Direct link to download TTML lyric file}` to update the lyric file. This action is deemed as resubmitting for review;
> 
> Comment in the Pull Request `/label {Label}` to add [appropriate labels](https://github.com/amll-dev/amll-ttml-db/labels);
> 
> > The bot's operation may have a delay of nearly 1-2 minutes. The bot will give a thumbs up to this comment when preparing to operate.
> 
> You can comment `/close {Reason}` to self-close this lyric submission; the reason is optional.
> 
> > *For all the above operations, you do not need to enter the brackets `{}`.*
***

# Using the Lyric Database

## AMLL Player [Recommended]

AMLL Player is a local client for Apple Music-like Lyrics, which can play local music and connect to WebSocket servers. [Go to download](https://github.com/amll-dev/applemusic-like-lyrics/actions/workflows/build-player.yaml)

AMLL Player has built-in lyric database search functionality. After importing local songs and editing lyric override information, you can search/import lyrics from the AMLL TTML DB.

## AMLL Page 

AMLL Page is the online web version of AMLL Player. It can play local music and connect to WebSocket servers. Except for plugin functions, it is basically consistent with the Player. [Go to learn more](https://github.com/apoint123/amll-page)

> Thanks to [@apoint123](https://github.com/apoint123) for developing the web version of AMLL!

## Apple Music-like Lyrics for BetterNCM [Stopped Maintenance]

Apple Music-like Lyrics for BetterNCM has built-in lyric sources from this repository. No manual configuration is required. You only need to pin the lyric source **AMLL TTML Word-Level Lyric Database (Multi-Source Aggregation)** to the top to use it.

> If you still wish to use the Netease Cloud client as your player while continuing to use the lyrics in this repository, please use [amll-bncm-ws-connector](https://github.com/Steve-xmh/amll-bncm-ws-connector) in conjunction with the AMLL Player.

### Mirror Sources

For certain reasons, the official source may occasionally experience issues such as being unable to search for lyrics, no lyrics found, or abnormal lyric return data. You can use the following mirror sources. Enter the following content in Plugin Settings - `Lyric Sources` - `Add from lyric source string`:

Author Mirror Source [@Steve-xmh](https://github.com/Steve-xmh)

```text
61ba6770-f02f-11ef-a3ae-5396943709e6|AMLL%20TTML%20Word-Level%20Lyric%20Database%20(stevexmh.net%20Mirror)||ttml|[https://amll-ttml-db.stevexmh.net/ncm/](https://amll-ttml-db.stevexmh.net/ncm/)[NCM_ID]

```

### Community Mirror Sources

You can also try the mirror sources provided by the community. Please refer to the site for specific usage methods. Thanks to [@HelloZGY](https://github.com/cybaka520) and [@Luorix](https://github.com/LuorixDev)!

[AMLL TTML DB Mirror Site](https://amlldb.bikonoo.com/mirror.html) By [@HelloZGY](https://github.com/cybaka520)

```text
19cf30a0-6206-11f0-b2b3-0d580aff0f69|Mirror%20Site||ttml|[https://amlldb.bikonoo.com/ncm-lyrics/](https://amlldb.bikonoo.com/ncm-lyrics/)[NCM_ID].ttml

```

[AMLL-TTML-DB Auto Mirror Site](https://amll.mirror.dimeta.top/) By [@Luorix](https://github.com/LuorixDev)

```text
06e48500-d086-11f0-bb6e-451fd0fc9216|Dimeta%20Mirror%20Site%20v1||ttml|[https://amll.mirror.dimeta.top/api/db/ncm-lyrics/](https://amll.mirror.dimeta.top/api/db/ncm-lyrics/)[NCM_ID].ttml

```

## UniLyric [Most Adaptable]

UniLyric is not only a versatile lyric converter but can also serve as the lyric sending end for AMLL Player. Its working principle is to obtain the song title, artist name, and playback progress of the track currently playing on the system by listening to [SMTC](https://learn.microsoft.com/en-us/windows/uwp/audio-video-camera/integrate-with-systemmediatransportcontrols) (if the SMTC sender has set it). Therefore, as long as your player supports SMTC, you can use it. Moreover, UniLyric integrates multiple lyric sources including AMLL TTML DB and can search automatically. It can be said to be the easiest-to-use database search party and AMLL Player lyric sending end currently available. [Go to learn more](https://github.com/apoint123/Unilyric)

## Integrate into Other Projects

> [!TIP]
> Although it is not mandatory, we hope that when you use this lyric database, you can add a link or description pointing to this repository or derivative projects in your project, or display the lyric author information in each lyric file (which can all be read in the metadata), so that more people can discover and build this lyric database. This will give us immense help.

If you want to integrate this lyric database, you can obtain the lyric files through the folders of the corresponding platforms, using your music ID for the corresponding platform.

Currently, lyric indexing for the following platforms is supported:

* [Netease Cloud Music](https://www.google.com/search?q=./ncm-lyrics) - [`ncm-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/ncm-lyrics)
* [QQ Music](https://www.google.com/search?q=./qq-lyrics) - [`qq-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/qq-lyrics)
* [Apple Music](https://www.google.com/search?q=./am-lyrics) - [`am-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/am-lyrics)
* [Spotify](https://www.google.com/search?q=./spotify-lyrics) - [`spotify-lyrics/`](https://github.com/amll-dev/amll-ttml-db/tree/main/spotify-lyrics)

Each lyric file has automatically generated lyric files of different formats, distinguished by file suffixes:

* `.ttml` - Original TTML lyric format
* `.lrc` - LyRiC lyric format
* `.yrc` - Netease Cloud Music word-level lyric format
* `.qrc` - QQ Music word-level lyric format
* `.lys` - Lyricify Syllable word-level lyric format
* `.eslrc` - ESLrc word-level lyric format

You can obtain the lyric file for your corresponding platform music ID through the following direct link:

> `https://raw.githubusercontent.com/amll-dev/amll-ttml-db/refs/heads/main/[Corresponding Platform Lyric Folder]/[Music ID].[Suffix]`

If you need to retrieve all lyric files from the establishment of the database to the present, you can access the [raw-lyrics/](https://www.google.com/search?q=./raw-lyrics/) folder. The files inside are named as `[Submission UNIX Timestamp]-[Submitter Github ID]-[8-character random ID].ttml`. Or retrieve through [`raw-lyrics-index.jsonl`](https://github.com/amll-dev/amll-ttml-db/raw/refs/heads/main/metadata/raw-lyrics-index.jsonl) in the [metadata/](https://www.google.com/search?q=./metadata) folder, which contains the metadata of all lyric files, and they are listed in chronological order from oldest to newest from top to bottom.

At the same time, under each platform folder, there is also an `index.jsonl` storing basic information, which stores all basic lyric information belonging to that platform line by line, arranged in the order of the original lyric files, and also lists all historical lyric information.

---

# Sharing License

The external data part of this repository is shared following the original data provider's sharing license, and the part written autonomously by contributors is shared using the [CC0 1.0 Sharing License](https://github.com/amll-dev/amll-ttml-db?tab=CC0-1.0-1-ov-file).

---

# Acknowledgments

Thanks to all users interested in AMLL ecosystem works, and you are also welcome to join the AMLL Friends and Family QQ Group `719423243` to participate in discussions.

Thanks to all the contributors who provided lyrics for building this repository!
