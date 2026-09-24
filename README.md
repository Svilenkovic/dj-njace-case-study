<a href="https://djnjace.svilenkovic.rs/"><img src="media/cover.jpg" alt="DJ Njace, home page on a laptop and a phone" width="100%"></a>

# DJ Njace

Demo site for a DJ: the home page moves through a film as you scroll, with prices laid out by event type and an inquiry form.

**[djnjace.svilenkovic.rs](https://djnjace.svilenkovic.rs/)** · [Case study (in Serbian)](https://svilenkovic.com/radovi/dj-njace) · [Srpski](README.sr.md)

> [!NOTE]
> My own demo. The source code is private. This page describes the idea and how it is built.

<table>
  <tr><td><b>Client</b></td><td>Own demo</td></tr>
  <tr><td><b>Industry</b></td><td>DJ for birthdays, slava celebrations, weddings and proms</td></tr>
  <tr><td><b>Location</b></td><td>Vranje, Serbia</td></tr>
  <tr><td><b>Type</b></td><td>Scroll-film website with a booking form</td></tr>
  <tr><td><b>My role</b></td><td>Concept, design, development, SEO and hosting</td></tr>
  <tr><td><b>Stack</b></td><td>Next.js 16, React 19, Tailwind, nginx, ffmpeg</td></tr>
</table>

## About the project

DJ Njace is a demo I built to show a complete site for a performer, from the first frame to a sent inquiry. The story is a DJ from Vranje who plays birthdays, slava celebrations, weddings, proms and company parties. The site is organized around what people ask a DJ first: is the date free, what does it cost and does the equipment come along.

The first version had a real 3D scene in the browser, and I took it out: it stuttered whenever a new object came into view, showed only a narrow strip of the scene on an upright phone and needed extra code to cover both. Now the background is a film that moves with the scroll. On desktop it is a 192-frame video in which every frame is a keyframe, so scrubbing never waits on decoding. Phones cannot seek video that precisely, so they get 84 WebP frames drawn on a canvas, and with reduced motion or data saver on there is a still image.

## What I built

- A home page about 9,000 px tall in six bands, with the band titles as real HTML over the film
- A price page organized by event type, with what each option includes and Offer data built from the same record as the visible price
- About fifteen landing pages by event type, city and genre, 23 URLs in the sitemap
- An inquiry form with server-side validation, a honeypot field and a per-IP rate limit
- No-cache HTML and a new file name for every version of the film, added after an old cached bundle kept autoplaying the video on a phone
- A guide line along a Catmull-Rom curve that draws itself on scroll, written by hand without an animation library

## Results

| | Performance | Accessibility | Best practices | SEO |
| :-- | :-: | :-: | :-: | :-: |
| Mobile | 99 | 100 | 100 | 100 |
| Desktop | 100 | 100 | 100 | 100 |

PageSpeed Insights, lab test of the live site, September 2026. Security headers: 6 of 6. HTML validator: no errors. axe accessibility check: no violations. Structured data: `EntertainmentBusiness`, `FAQPage`, `LocalBusiness`, `MusicGroup`, `Person`.

## Screenshots

<table>
  <tr>
    <td width="68%" valign="top"><img src="media/desktop.webp" alt="DJ Njace, home page on a 1440 px screen"></td>
    <td width="32%" valign="top"><img src="media/mobile.webp" alt="DJ Njace, home page on a phone"></td>
  </tr>
</table>

<img src="media/inner-1.webp" alt="Banner &quot;Pult spreman pre prvog gosta&quot; (Booth ready before the first guest): frame shifted, text is real HTML">
<sub>Banner "Pult spreman pre prvog gosta" (Booth ready before the first guest): frame shifted, text is real HTML</sub>

<img src="media/inner-2.webp" alt="Banner &quot;Prva pesma, i parket je već pun&quot; (First song, and the floor is full): song requests agreed in advance">
<sub>Banner "Prva pesma, i parket je već pun" (First song, and the floor is full): song requests agreed in advance</sub>

---

<sub>Built by [D. Svilenković](https://svilenkovic.com).</sub>
