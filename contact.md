---
layout: default
title: Contact us
nav_order: 9
description: contact us
permalink: /contact
search_exclude: true
---
## Contact form
Please use our contact form below if you have any questions, comments or feedback.

<form class="mb-5"
  action="https://formspree.io/f/xyyldkpg"
  method="POST"
>

<input type="hidden" name="_subject" value="mitkb feedback" />
  <div class="container">
    <div class="row mb-2">
      <div class="col">
        Email:
      </div>
      <div class="col">
        <input type="text" name="_replyto" placeholder="Your email" />
      </div>
    </div>

    <div class="row mb-2">
      <div class="col">
        Message:
      </div>
      <div class="col">
        <textarea name="message" cols="50" rows="15" placeholder="Write your message"></textarea>
      </div>
    </div>

    <input type="text" name="_gotcha" style="display:none" />

    <div class="row">
      <div class="col">
        <input type="submit" value="Send Message" class="btn btn-primary rounded-0 py-2 px-4" />
        <span class="submitting"></span>
      </div>
    </div>

  </div>

</form>

Powered by
<img src="{{ site.baseurl }}/assets/images/formspree.webp" alt="FORMSPREE" width="16">
[Formspree](https://formspree.io/)

## Bug reports
Please use GitHub issues if you find any technical issues with the site.
<p>
<img src="{{ site.baseurl }}/assets/images/github.webp" alt="Github" width="16">
<a href="https://github.com/ncrnas/mitkb/issues/">
GitHub issues
</a>
</p>
