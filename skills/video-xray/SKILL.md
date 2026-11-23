---
name: video-xray
description: Take any viral video apart shot by shot (how each shot was made, the hook, the beat map, the text on screen, the sound, why it works) and then make YOUR version of it in Cadabra AI, cut on the original's measured rhythm, with your face, your topic or your product. No install, it runs through the Cadabra connector in the chat. Use when someone shares a reel, TikTok, Short or ad and asks how it was made, whether it is AI, why it went viral, how to make one like it, or to remake it.
---

# Video X-Ray

Most tools stop at a report. This one stops at a finished video.

1. **X-ray** (free): every cut measured, one still from inside every shot,
   the pace, whether the cuts land on the music, the hook scored.
2. **Read it**: for every shot, how it was made and what job it does.
   Then the Viral DNA card: the one-line idea, the hook, the beat map, why
   it works, what is weak.
3. **Remake** (priced before anything is spent): the same structure and
   rhythm, the user's own content, made with Cadabra's engines and cut on
   the original's timeline into one vertical film in their gallery.

It runs in any chat that has the Cadabra AI connector (Claude, ChatGPT,
Claude Code). The X-ray costs nothing. Making the new video needs a Cadabra
AI package, because that is where the engines are.

Answer in the user's language, Hebrew included. Hebrew is written right to
left.

## 0. Rights, before anything

The reference video belongs to someone else. You study its structure,
pacing and techniques. You never re-post its footage, its music, its
characters, its brand or the face of anyone in it. The remake is made from
material the user owns or generates. Only put a real person in the remake
from a photo they gave of themselves, or of someone who agreed. If the user
asks to copy a creator's video one to one, say what you will do instead:
same structure, their own world.

## 1. Get the video

The tools need a DIRECT link to the video file, not the page it sits on.

- A file the user attached in ChatGPT: pass it to `cadabra_upload_file`
  in `chat_files`.
- A file on their computer: `cadabra_upload_file` with no arguments opens
  an upload button. If none appears, send them
  https://livinginmovie.com/mcp/upload, they drop the file there and paste
  the link back.
- A TikTok, Instagram or YouTube PAGE link does not work by itself. Ask
  them to save the video (most apps have Save or Download) and upload it.
- In Claude Code, if the user has the file on disk, read it and upload the
  bytes.

Also ask, in one line, for what the platform shows: views, likes,
comments, shares, posting date. A video with 2M views and 300 comments is a
different lesson from one with 40K views and 4K comments.

## 2. The X-ray (free, always first)

Run these before saying anything about the video:

1. `cadabra_inspect` with `include: ["duration", "shots", "beats"]` on the
   video link. You get the cut list (start, end, length and movement of every
   shot), the pace and whether the cutting speeds up, how many cuts land on a
   beat, and one still from inside each shot, labelled. Look at EVERY still.
   A long shot with no cuts (a talking head with screens laid over it) gets
   extra stills from inside it, because the picture can change without a
   cut. For a shot you still cannot judge, call `cadabra_inspect` again with
   `include: ["frames"]` and `frame_count: 8`.
   The same call reads the FILE's own metadata: a generator that signed its
   output, an AI label, a content credential, the app or phone that saved
   it last.
2. `cadabra_hook_check` on the same link: the first three seconds, scored.
3. The words. If the video has burned-in captions, read them from the stills.
   If it is spoken and the captions are not on screen, offer
   `cadabra_transcribe` (it costs a little: show its quote and wait for a
   yes). Never guess the words.

Never describe something you did not see in a still or read in the words.
If two cuts are far apart and you only saw one still between them, say so.

## 3. How each shot was made

For each shot, pick ONE of these and give a confidence (for example "AI
video, about 80%"). Say what you saw that decided it.

| Kind | What gives it away |
|---|---|
| Filmed on a phone or camera | Handheld shake, autofocus breathing, motion blur on fast hands, mixed real light, sensor noise in the dark areas, a real room with mess in it, a face that stays the same person when it turns |
| AI video | Hands and fingers that merge or change count, text that turns into almost-letters, objects that melt into each other, physics that floats (hair, water, cloth), skin too smooth, the same perfect light from every angle, shots that run almost exactly 5, 8, 10 or 15 seconds |
| Talking avatar or lip-sync | The head stays locked while only the mouth and eyes move, the same framing and background for the whole talk, teeth that blur, hands that barely move or loop |
| Screen recording | An app or browser interface, a cursor, scrolling, typing |
| Motion graphic or text card | Perfect type, flat shapes, charts that draw themselves, nothing a camera could film |
| A still with a move | One picture with a slow zoom or pan and no parallax (near and far things move together) |
| Footage from a film or show | A shot clearly cut from a movie, a series or the news |

**Trust in this order.** What the file says (a generator's name in its
metadata) beats what was measured (cuts, movement, length), and what was
measured beats what a still looks like. A content credential alone does not
mean AI, because cameras and editors sign them too. A file with no metadata
proves nothing: platforms strip it.

**Runs of the same take.** Several shots in a row of the same person, same
framing, same place, cut a beat apart, are jump cuts inside ONE take. Judge
them together, and in the remake film or generate them once and cut.

A shot can be two things at once. Filmed, then changed by AI (a swapped
face, a restyle, a new background) counts as filmed with an AI edit: say
both. On a video that was re-saved by a platform, the noise clues get
weaker, so lean on hands, text and physics.

Also mark, for every shot:

- **Its job**: hook, setup, proof, turn, payoff or call to action.
- **What is laid on top**: captions (style, where they sit, word by word or
  a line at a time), titles, stickers, a picture inside the picture, arrows,
  a progress bar. Quote every word of on-screen text.

## 4. The Viral DNA card

Write this for the user, short, with a timestamp on every claim:

1. **The idea in one line.** If it cannot be said in one sentence, it is not
   why the video spread.
2. **The hook, 0 to 3 seconds.** The first frame, the first words, the first
   movement, the first text, and the second the promise lands. Which kind:
   a question, a surprise, a bold claim, a result shown first, a face mid
   reaction, a number.
3. **The beat map.** Shot by shot or block by block: what the viewer gets at
   each moment, where the turn is, where it peaks, where the payoff sits.
4. **The rhythm, in numbers.** Shots, average shot, first cut, the longest
   hold and what it holds on, accelerating or steady, cuts on the beat or on
   the words.
5. **What keeps people watching.** Name each device with its second: an open
   question answered at the end, a numbered list ("3 of 3"), a countdown, a
   pattern change every few seconds, before and after, the result held back.
6. **Sound.** A real voice or a generated one, music or silence, where the
   sound effects hit, and whether the music drives the cuts.
7. **The ending.** The last frame, the call to action, whether it loops back
   into the first frame.
8. **Why it works**: three points, each with the second it happens.
9. **What is weak** and the one change that would make it stronger.

## 5. The remake board

Ask the user three things, in one message: what their version is about (or
which product), whether they want to be in it (their photo, or their avatar
in Cadabra), and the language of the words on screen and in the voice.

Then keep the structure and swap the content. Same number of beats, same
job per beat, same rhythm, their world. For every shot write a line:

| Original shot | Route in Cadabra | What you send |
|---|---|---|
| AI video | `cadabra_generate_image` for the first frame, then `cadabra_generate_video` from it | A prompt you write from the still: shot size, camera, the action, the light, the place, 9:16, with the user's subject swapped in. Length matched to the measured shot. |
| Filmed shot of a person talking | The user films it on their phone, or `cadabra_generate_avatar` with their avatar | A shooting note (where the phone stands, the light, the line to say) or the avatar script |
| Filmed b-roll or product | `cadabra_generate_video`, or the user films it | The prompt, or the shot list |
| Screen recording | The user records their own screen | What to record, for how many seconds |
| Text card, title, chart | Titles in `cadabra_assemble`, or `cadabra_compose` for a designed graphic | The exact words and where they sit |
| A still with a move | `cadabra_generate_image`, then let the edit move it | The prompt |
| Music | `cadabra_generate_music_v6` | Style and the measured BPM, so the new cuts land where the old ones did |
| A spoken voice | Their own recording, or `cadabra_eleven_v4_speak` with their voice | The script |

Write the words for the new version yourself, in the original's shape: if
the hook was a number and a promise, theirs is a number and a promise.

**Spend only where the picture needs it.**

- A still with a move is ONE picture. Make the picture and let the edit
  zoom or pan it. Do not pay for video there.
- A run of jump cuts is one take: one recording, or one generation, cut.
- Consecutive shots with the same character in the same place can often be
  ONE multi-shot generation, when the engine allows it. Quote it both ways
  and take the cheaper one that still holds the face.
- Text, captions, titles, numbers and arrows are NEVER asked for inside a
  generated picture. Every prompt says no text on screen, and the words
  come in the edit, where they stay editable, spelled right and in any
  language, Hebrew right to left included.

**How to write each prompt.** Shot size, angle and where the subject stands;
then one action and how it ENDS ("she turns to the lens and holds the
look"); then the camera move; then the light and the place; then 9:16. Write
acting as what can be seen (raised eyebrows, a slow smile, hands frozen
mid-air), not as feelings. One subject per sentence. Say what is there, not
what is not, apart from "no text, no logos".

## 6. Price, then one shot, then the rest

1. Run `cadabra_quote` for the paid steps and show the user the total
   before anything is made. Wait for a clear yes. Prefer the cheaper
   resolution unless they ask for more.
2. Make the HOOK shot first. Look at it with `cadabra_inspect`
   (`include: ["frames"]`) and with the user: right face, right look, does it
   stop the thumb? Only then make the rest. One shot is the cheapest place
   to find out the prompt needs one more word.
3. A shot that came back wrong is not retried without a new yes.

## 7. Cut it on the original's rhythm

`cadabra_assemble` with the new clips in order, each trimmed to the length
the X-ray measured for the shot it replaces, the titles and captions from
the board, and the music. Put the hook title in second zero. Show its quote
first.

When it lands:

1. `cadabra_inspect` with `include: ["shots"]` on the new film, and compare
   the rhythm with the original's: shot count, first cut, average shot.
2. `cadabra_hook_check` on the new film.
3. Show the user both side by side: their version and the X-ray of the
   original, with what changed.

## 8. Several videos at once

When the user sends two or more references, X-ray each one, then put them
in one table (length, shots, average shot, first cut, hook kind, text on
screen, sound, views if known, call to action), name the pattern they
share, say which is strongest and why from the stills, not only from the
view count, and build ONE remake that takes the best of each.

## 9. How sure to be

The X-ray is measured. The judging is yours, from stills, so say how sure
you are. Re-saved social video is the hardest case: the platform erases the
fine noise a camera leaves, so a plain phone shot on a tripod can pass for
AI or 3D. When it matters, look at more stills of that shot before calling
it.

## 10. Never

- Never re-post, re-upload or re-use the reference's footage, music,
  characters, brand or people.
- Never spend without a quote and a yes.
- Never claim how a shot was made with more certainty than the stills give.
- Never put text over a face in the remake.
- Never promise views. The X-ray explains why a video worked; it does not
  predict the next one.
