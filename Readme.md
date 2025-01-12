<p align="center"><a href="https://rahul-pranjal-wedding-invite.web.app/"><img src="https://res.cloudinary.com/dytbosrbw/image/upload/v1699181308/favicon_vv8fch.png" width="150px" height="150px"/></a></p>
<h1 align="center"><a href="https://rahul-pranjal-wedding-invite.web.app/">Wedding Invitation</a><img src="https://res.cloudinary.com/dytbosrbw/image/upload/v1699090976/wedding_cdg95p.gif" width="22px" height="22px"  <br> <br> SAVE THE DATE: DEC 04, 2023 <br> <a href="https://rahul-pranjal-wedding-invite.web.app/">Rahul Pranjal widding invitation</a></h1>

Welcome to our wedding invitation website repository! This project is built with HTML, CSS, and JavaScript to create a beautiful and interactive platform for inviting your guests to celebrate this special day with you. The website incorporates various features, including an RSVP section to help you manage your guest list. We've also utilized the ScrollReveal library to add elegant scrolling animations and bring an extra touch of magic to the site. Feel free to explore the code, customize it to your liking, and use it as a template for your own wedding invitation website. Wishing you a wonderful wedding journey!

## Wedding Invitation

<details>
  <summary><strong>View Invitation</strong></summary>
  <a href="https://rahul-pranjal-wedding-invite.web.app/"><img src="https://res.cloudinary.com/dytbosrbw/image/upload/v1699241763/Rahul_Pranjal-Wedding-Celebration_ewxofb.png" /></a>
</details>

With the divine grace of the Almighty,
I cordially invite you and your family to
my wedding to be held on **04th December at [jangid bhawan](https://maps.app.goo.gl/wPVwUUrKnYUMy24D7), Akola from 7:00 PM** onwards.

- [Download](invitation/widding-invitation-04-Dec.pdf) the Invitation card

- Find [venue](https://maps.app.goo.gl/wPVwUUrKnYUMy24D7) on Google map

- Visit the [website](https://rahul-pranjal-wedding-invite.web.app/) for more details

## Features

- Elegant design
- RSVP section for managing your guest list
- Enchanting animations using the ScrollReveal library
- A countdown timer in `script.js` for the big day.
- Background music for an immersive experience.
- Gmail-to-Google Sheets script for tracking RSVP responses.
- SweetAlert for delightful pop-up notifications.
- Google Calendar events for timely notifications.

## Guide


2. Customize the CSS color scheme to match your wedding theme.

```css
: root {
  /*========== Colors ==========*/
  /* favorite color */
  --hue-color: 250;

  /* HSL color mode */
  --primary-color: hsl(var(--hue-color), 69%, 61%);
  --primary-color-lighter: hsl(var(--hue-color), 92%, 85%);
  --second-color: hsl(350, 43%, 43%);
  --title-color: hsl(var(--hue-color), 8%, 15%);
  --text-color: hsl(var(--hue-color), 8%, 45%);
  --text-color-light: hsl(var(--hue-color), 8%, 65%);
  --body-color: hsl(var(--hue-color), 60%, 95%);
  --scroll-bar-color: hsl(var(--hue-color), 12%, 90%);
  --scroll-thumb-color: hsl(var(--hue-color), 12%, 80%);
}
```

3. Replace the date in `script.js` with your wedding date to have a timer running for your big day.

``` js
// Set the date we're counting down to
var countDownDate = new Date("dec 04, 2023 19:00:00").getTime();
```

4. Change the music by replacing the audio file in the 'assets/mp3' folder.

```HTML
<!--=============== music ===============-->
<div class="music">
  <audio
    Autoplay
    controls
    src="./assets/mp3/song.mp3"
    id="my_audio"
    loop="loop"
  ></audio>
</div>
```

5. Add the ScrollReveal library for enchanting animations.

``` js
/*===== SCROLL REVEAL ANIMATION =====*/
const sr = ScrollReveal({
  origin: "top",
  distance: "1.5rem",
  duration: 2000,
  delay: 200,
  // reset: true
});

sr.reveal(`.rahul`, { origin: "left", delay: 700 });
sr.reveal(`.pranjal`, { origin: "right", delay: 700 });
sr.reveal(`.gif,.home_txt`, { delay: 1300, origin: "top" });
sr.reveal(`.top-right-decoration,.top-left-decoration`, {
  origin: "left",
  delay: 2200,
});
sr.reveal(`.responsive-table__row`, { interval: 200 });
sr.reveal(`.table_container`, { delay: 100, origin: "top" });
sr.reveal(`.happiness,.hindi_text`, { delay: 400, origin: "bottom" });
sr.reveal(`.social__links`, { delay: 1000, origin: "bottom", interval: 200 });
sr.reveal(`.newsletter__description,.home__bottom`, {
  origin: "left",
  delay: 400,
});
sr.reveal(`.newsletter__form,.CTA`, { origin: "right", delay: 400 });
```

6. Set up and configure the Gmail-to-Google Sheets script for tracking RSVP responses.

```js
const scriptURL =
  "https://script.google.com/macros/s/AKfycbxnUL9qcht2oEF074cG1zCfv2IJN0zCFjbCSjz7365LQrdNdLA3P_CjBeDg1dBsyMIc/exec";
const form = document.forms["newsletter"];
const loading = document.querySelector(".loading");
//const join = document.querySelector('.button');
form.addEventListener("submit", (e) => {
  e.preventDefault();
  document.querySelector(".button").disabled = true;
  loading.classList.add("d-block");
  fetch(scriptURL, { method: "POST", body: new FormData(form) })
    .then(function (data) {
      // from reset
      form.reset();
      // on success
      loading.classList.remove("d-block");
      Swal.fire({
        icon: "success",
        text: "Thank You for Joining Our Celebration!",
      });
      document.querySelector(".button").disabled = false;
    })
    .catch(function (data) {
      // from reset
      form.reset();
      // on success
      loading.classList.remove("d-block");
      Swal.fire({
        icon: "error",
        text: "Oops! Something Went Wrong.",
      });
      document.querySelector(".button").disabled = false;
    });
});
```

8. Deploy the website to your hosting platform of choice.
   <br> <br> <br><br>

### Gmail-to-Google Sheets Script

- Open Google Sheets and create a new Google Apps Script.
- Write your Gmail-to-Google Sheets script to fetch and parse RSVP emails, then write data to your Google Sheets.
- Save the script and set up triggers for automatic execution.
- For integrating a Gmail-to-Google Sheets script into your wedding invitation website, you can refer to the [TiagoGouvea/gmail-to-google-sheets-script](https://github.com/TiagoGouvea/gmail-to-google-sheets-script) repository for a well-documented example and implementation guide.

- Please follow the instructions and adapt the script to your specific needs, such as tracking RSVP responses from your guests.

## Screenshot

![Website Screenshot](https://res.cloudinary.com/dytbosrbw/image/upload/v1699096716/home_txyron.png)

![Website Screenshot](https://res.cloudinary.com/dytbosrbw/image/upload/v1699096716/footer_e5oimq.png)

---

Feel free to explore the code, make it your own, and use it as a template for your own wedding invitation website. Wishing you a wonderful wedding journey!
<br><br><br>

#### With warm regards, <br>

[aarjaycreation](https://aarjaycreation.com/)
"# wedding-invite" 
"# wedding-invite" 
"# wedding-invite" 
