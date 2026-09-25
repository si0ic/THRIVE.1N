# THRIVE — Heat Health Risk Platform

THRIVE is a Vercel-ready heat-health risk platform using the existing Open-Meteo weather flow, OpenStreetMap/OpenLayers map, nearby hospital/park discovery and the existing client-side heat-risk model.

## Registration flow

The public **Register** form now submits directly to Formspree:

`https://formspree.io/f/xzdoyypp`

The submission includes:

- name, phone and email
- selected location and coordinates
- current THRIVE risk level and score
- risk explanation shown in the UI
- UTM attribution and landing URL
- explicit consent

The form keeps the existing THRIVE confirmation dialog and validation, but it no longer sends registrations to the THRIVE alert API. Form submissions are handled manually from the Formspree inbox.

## Vercel deployment

The project keeps the existing Vercel build setup:

```bash
npm install
npm run build
```

Deploy the project root to Vercel. No Exotel credentials are required for the public registration form. The `vercel.json` file no longer schedules automatic alert checks.

## Heat-map image

The supplied India heat-map image is included as `india-heat-map.jpg` and is displayed in the existing **Heat can kill.** evidence section. The build script copies it into `dist/`.

## Legacy backend/admin code

The existing Supabase registration/admin and Exotel alert files are retained in the repository for backwards compatibility and maintenance, but the public THRIVE registration flow does not call them and the Vercel deployment no longer runs the old automatic alert cron. The public navigation no longer exposes the legacy Emergency Alerts console.

For this version, **Formspree is the operational inbox** for user information; there is no automatic SMS or phone-call requirement.

## Privacy

The registration section explains that submitted information is processed by Formspree and may be retained by the THRIVE team for manual follow-up. Review the Formspree account settings and privacy controls attached to the endpoint for the current retention and notification configuration.

## Core frontend behavior preserved

The existing location search, automatic location flow, OpenLayers map, Open-Meteo weather data, heat-risk score, risk explanations, nearby hospitals/parks, evidence section, print/copy tools, responsive design and cookie preferences remain in place.
