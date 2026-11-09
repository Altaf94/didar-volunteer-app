# Didar Volunteer App

A React Native (TypeScript) mobile app for managing volunteer assignments for Didar Mubarak events in northern Pakistan, from data upload and validation to approvals, badge printing and dispatch.

## Context

Volunteers are sourced through a hierarchy of National, Regional, Local Councils and Jamat Khanas across six regions (Gilgit, Hunza, Gupis, Ishkoman, Lower Chitral, Upper Chitral). Each volunteer is assigned an access level (Stage, Pandal, Outside Holding Area, Outside Area, Health Area), shown by a band colour. See [`docs/VOLUNTEER_SYSTEM.md`](docs/VOLUNTEER_SYSTEM.md) for the full design.

## Features

- Role-based access: View Only, Maker (upload, validate, approve/reject, submit) and Checker (review, print badges, dispatch)
- Volunteer data upload via Excel with automatic validation (CNIC lookup, duplicate duties, discrepancies)
- Maker and Checker home screens, volunteer review, badge printing and package dispatch screens
- Dashboard with stats cards for leadership
- JWT token handling and auth context; user management screen
- Design docs: system overview, flow diagrams and test cases in `docs/`

## Tech stack

- **Mobile:** React Native, TypeScript
- **Navigation:** React Navigation (stack + bottom tabs)
- **State:** React Context (Auth, Volunteer)
- **Storage:** AsyncStorage
- **Icons:** lucide-react-native, react-native-vector-icons
- **Backend:** FastAPI service (separate repository)

## Project structure

```
src/
  screens/volunteer/   Maker, Checker, Review, Upload, PrintBadges, DispatchPackages, Dashboard
  screens/auth/        Login
  components/          Header, CustomInput, CustomModal, volunteer/ cards, filters, file upload
  context/             AuthContext, VolunteerContext
  services/            api, volunteerApi, tokenService
docs/                  VOLUNTEER_SYSTEM.md, FLOW_DIAGRAMS.md, TEST_CASES.md
```

## Getting started

```bash
yarn install
cd ios && pod install && cd ..   # iOS only
yarn start
yarn android     # or: yarn ios
```

## Author

Built by **Altaf Hassan**, Software Engineer (React Native & full-stack). [Portfolio](https://altaf94-portfolio.netlify.app) · [LinkedIn](https://linkedin.com/in/altaf-hassan)
