# Rock RMS Personalized Hero Banner

A reusable Rock RMS hero banner component that displays a personalized greeting, randomized background image, blur overlay, and responsive styling.

This component is intended for dashboards, internal landing pages, ministry workspaces, or any Rock RMS page where a more welcoming and personalized header is helpful.

## Features

* Personalized greeting using Rock Lava
* Time-based greeting logic
* Random background image on each page load
* Placeholder image paths for public repo use
* Blur and dark overlay for text readability
* Responsive mobile styling
* No external dependencies

## Preview

The component renders a rounded hero banner with centered text over a randomized background image.

Example greeting:

```text
Good morning, Alex!
```

Example subtitle:

```text
Empowering ministry through connection.
```

## How It Works

### Time-Based Greeting

The banner uses Lava to determine the current hour and display the appropriate greeting.

```liquid
{% assign currentHour = 'Now' | Date:'H' | AsInteger %}

{% if currentHour < 12 %}
  {% assign greeting = 'Good morning' %}
{% elseif currentHour < 17 %}
  {% assign greeting = 'Good afternoon' %}
{% else %}
  {% assign greeting = 'Good evening' %}
{% endif %}
```

Greeting windows:

| Time                | Greeting       |
| ------------------- | -------------- |
| 12:00 AM – 11:59 AM | Good morning   |
| 12:00 PM – 4:59 PM  | Good afternoon |
| 5:00 PM – 11:59 PM  | Good evening   |

### User Personalization

The banner uses the current person’s nickname when available and falls back to their first name.

```liquid
{% assign nickname = CurrentPerson.NickName | Default:CurrentPerson.FirstName | Default:'there' %}
```

If neither value exists, the banner will display:

```text
Good morning, there!
```

### Random Background Image

The JavaScript selects one image from the `heroImages` array each time the page loads.

```javascript
const heroImages = [
  "/assets/hero-banner-01.jpg",
  "/assets/hero-banner-02.jpg",
  "/assets/hero-banner-03.jpg"
];
```

Replace these placeholder paths with your own image paths, CDN links, or theme asset URLs.

## Installation

1. Add an HTML Content block to a Rock RMS page.
2. Paste the full HTML, CSS, Lava, and JavaScript into the block.
3. Replace the placeholder image paths in the `heroImages` array.
4. Save and publish the page.

## Customization

### Change the Subtitle

Update this line:

```html
<p class="hero-banner-subtitle">
  Empowering ministry through connection.
</p>
```

### Change the Image List

Replace the placeholder asset paths:

```javascript
const heroImages = [
  "/assets/hero-banner-01.jpg",
  "/assets/hero-banner-02.jpg",
  "/assets/hero-banner-03.jpg"
];
```

### Change Banner Height

Desktop height:

```css
.hero-banner-image {
  height: 205px;
}
```

Mobile height:

```css
.hero-banner-image {
  height: 145px;
}
```

### Change Blur Strength

```css
backdrop-filter: blur(8px);
-webkit-backdrop-filter: blur(8px);
```

Suggested values:

| Blur | Effect   |
| ---- | -------- |
| 4px  | Subtle   |
| 8px  | Balanced |
| 12px | Strong   |

## Notes

This component uses standard HTML, CSS, JavaScript, and Rock Lava. It does not require a custom plugin.

Because the background images are randomized client-side, users may see a different image each time the page loads.
