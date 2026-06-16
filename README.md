# Pet Registry Portal

A Dockerized Symfony API and Vue client for submitting pet records through two form implementations: a component-based generic form and a Vuetify form variant.

## Architecture

```text
Vue forms -> Symfony pet endpoint -> request validation -> JSON response
```

## Run with Docker

```bash
docker compose up --build
```

- Client: `http://localhost:8080`
- Generic form: `http://localhost:8080/`
- Vuetify form: `http://localhost:8080/vuetify-pet-form`
- API: `http://localhost:8000`

Stop the stack with `docker compose down`.

## Repository map

- `pet-registry-client/src/components/pet/form` — generic form sections and breed fallback.
- `pet-registry-client/src/components/VuetifyPetForm.vue` — alternate UI implementation.
- `pet-registry-server/src/Controller/Api/v1/PetController.php` — API entry point.
- `pet-registry-server/src/Request/PetCreationRequest.php` — request validation.

## Boundaries

The repository contains committed Symfony development-cache output under `var/cache`; that generated material is not application architecture and should be removed in a future cleanup. Persistence, authentication, production validation, and runtime behavior were not verified. The Docker stack was not run during the portfolio review.
