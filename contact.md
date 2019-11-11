---
title: Contact Us
layout: page
scripts: |
  <script src='https://www.google.com/recaptcha/api.js'></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.19.1/jquery.validate.min.js"></script>
  <script src="/assets/custom/js/contact.js"></script>

---

<form id="contactform" onsubmit="event.preventDefault();" novalidate>
  <div class="row">
    <div class="col-md-6">
      <div class="form-group">
        <label for="name">Name</label>
        <input type="text" class="form-control" name="name" id="contactform-name" placeholder="" value="" required>
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" class="form-control" name="email" id="contactform-email" placeholder="" value="" required>
      </div>
      <div class="form-group">
        <label for="subject">Subject</label>
        <div class="input-group">
          <select class="form-control" name="subject" id="contactform-subject" required>
            <option value="">Select One</option>
            <option value="Summer Camp">Summer Camp</option>
            <option value="Reservations">Reservations</option>
            <option value="Fall Fest">Fall Fest</option>
            <option value="Training">Training</option>
            <option value="Other">Other</option>
          </select>
        </div>
      </div>
    </div>
    <div class="col-md-6">
      <div class="form-group">
        <label for="message">Message</label>
        <textarea class="form-control" name="message" id="contactform-message" rows="12" required></textarea>
      </div>
      <div class="g-recaptcha"
        data-sitekey="{{ site.recaptcha }}"
        data-callback="ContactUs"
        data-size="invisible">
      </div>
      <div class="form-group">
        <button type="submit" class="btn btn-primary btn-block" id="contactform-send">Send</button>
      </div>
      <div class="alert alert-info fade hidden" role="alert" id="alert-response">
        <strong id="alert-headline"></strong> <span id="alert-text"></span>
      </div>
    </div>
  </div>
</form>
