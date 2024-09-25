# Save My Forms

Save My Forms helps detect and prevent form submissions by bot users. It utilizes the `@fingerprintjs/botd` library for bot detection and employs a honeypot technique with fake actions. Additionally, it monitors user interactions such as mouse movement, clicks, scrolling, key presses, and form changes to ensure the validity of submissions.

## Usage

To integrate **Save My Forms** into your Webflow page, simply add the following script tag:

```html
<script src="https://cdn.jsdelivr.net/gh/amplydevelopment/amply-save-my-form@57cc8ae0d9c1523db6447ab70e248c8a04fbfbe0/index.js"></script>
```

## API Reference

### 1. `amply-smf` attribute (required)

Add the `amply-smf="true"` attribute to your form element. Ensure that this attribute is applied directly to the form element, not the form block (form container).

### 2. `amply-smf-debug` attribute (optional)

Add the `amply-smf-debug="true"` attribute to your form element to enable debug mode. This will add two hidden input fields to your form:

- `amply-smf-debug-log`: Contains bot detection data.
- `amply-smf-is-bot`: Contains a bot detection flag.
- `amply-smf-debug-fill-seconds`: Contains the total time taken to fill out the form.

### 3. `amply-smf-action` attribute (optional)

Add the `amply-smf-action="YOUR_ACTUAL_ACTION_URL"` attribute to your form element if you want to use a custom action URL for form submission.

### 4. `amply-smf-min-form-change` attribute (optional)

Add the `amply-smf-min-form-change="NUMBER"` attribute to your form element. This specifies the minimum number of times a form change event should trigger. The default value is 2.

### 5. `amply-smf-min-key-up` attribute (optional)

Add the `amply-smf-min-key-up="NUMBER"` attribute to your form element. This specifies the minimum number of keyup events that should be triggered while filling out the form.

### 6. `amply-smf-min-form-fill-sec` attribute (optional)

Add the `amply-smf-min-form-fill-sec="NUMBER"` attribute to your form element. This specifies the minimum number of seconds required for filling out the form. If a user attempts to submit the form before the specified time has passed, submission will be blocked and the honeypot mechanism will be activated to detect and prevent bot submissions. The default value is 10.

### 7. `amply-smf-bot-alert` attribute (optional)

Add the `amply-smf-bot-alert="true"` attribute to any element you want to display when a bot is detected (e.g. a modal or banner). Save My Forms will add an `active` class to this element when bot activity is detected, so make sure to style the `active` class accordingly.


---

## Important Notes

- Ensure that your form has a fake action URL to help detect bots.
- **Save My Forms** is a JavaScript-based solution, meaning it will not function if JavaScript is disabled. Consider using a `<noscript>` tag to display a warning message for users with JavaScript disabled.
