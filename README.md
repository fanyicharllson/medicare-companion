# MediCare Companion 💊

Smart medication management system with OCR scanning, reminders, and family alerts.

## Tech Stack
- **Frontend:** Next.js 14, Tailwind, React Query, Clerk
- **Backend:** Express, PostgreSQL, Prisma
- **Deployment:** VPS + CI/CD

## Setup

### Prerequisites
- Node.js 18+
- PostgreSQL
- pnpm

### Installation
```bash
# Clone
git clone https://github.com/fanyicharllson/medicare-companion.git
cd medicare-companion

# Frontend
cd frontend
pnpm install
cp .env.example .env.local
pnpm dev

# Backend
cd ../backend
pnpm install
cp .env.example .env
npx prisma migrate dev
pnpm dev
```

### Environment Variables
See `.env.example` in each folder.

## Team
- FANYI CHARLLSON FANYI
- LUM NCHIFOR

## License
MIT
```

---

## **Frontend Structure**
```
frontend/
├── public/
│   ├── icons/
│   │   ├── icon-192.png
│   │   └── icon-512.png
│   └── manifest.json
├── src/
│   ├── app/
│   │   ├── (auth)/
│   │   │   ├── login/
│   │   │   │   └── page.tsx
│   │   │   └── register/
│   │   │       └── page.tsx
│   │   ├── (dashboard)/
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx (dashboard)
│   │   │   ├── medications/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── add/page.tsx
│   │   │   │   └── [id]/page.tsx
│   │   │   ├── adherence/
│   │   │   │   └── page.tsx
│   │   │   ├── family/
│   │   │   │   └── page.tsx
│   │   │   └── settings/
│   │   │       └── page.tsx
│   │   ├── layout.tsx
│   │   ├── page.tsx (landing)
│   │   └── globals.css
│   ├── components/
│   │   ├── ui/ (shadcn components)
│   │   ├── medications/
│   │   │   ├── MedicationCard.tsx
│   │   │   ├── MedicationForm.tsx
│   │   │   └── CameraScanner.tsx
│   │   ├── adherence/
│   │   │   ├── AdherenceCalendar.tsx
│   │   │   └── AdherenceChart.tsx
│   │   ├── layout/
│   │   │   ├── Navbar.tsx
│   │   │   ├── Sidebar.tsx
│   │   │   └── Footer.tsx
│   │   └── shared/
│   │       ├── LoadingSpinner.tsx
│   │       └── ErrorBoundary.tsx
│   ├── lib/
│   │   ├── api.ts (axios instance)
│   │   ├── utils.ts
│   │   └── validations/ (zod schemas)
│   │       ├── medication.ts
│   │       └── user.ts
│   ├── hooks/
│   │   ├── useMedications.ts
│   │   ├── useAdherence.ts
│   │   └── useNotifications.ts
│   ├── types/
│   │   └── index.ts
│   └── config/
│       └── constants.ts
├── .env.example
├── .env.local
├── next.config.js
├── tailwind.config.ts
├── tsconfig.json
├── package.json
└── pnpm-lock.yaml
```

---

## **Backend Structure**
```
backend/
├── src/
│   ├── config/
│   │   ├── database.ts
│   │   └── env.ts
│   ├── middleware/
│   │   ├── auth.ts (Clerk verification)
│   │   ├── validate.ts (Zod)
│   │   └── errorHandler.ts
│   ├── routes/
│   │   ├── index.ts
│   │   ├── medications.ts
│   │   ├── adherence.ts
│   │   ├── family.ts
│   │   ├── interactions.ts
│   │   └── notifications.ts
│   ├── controllers/
│   │   ├── medicationController.ts
│   │   ├── adherenceController.ts
│   │   ├── familyController.ts
│   │   └── notificationController.ts
│   ├── services/
│   │   ├── medicationService.ts
│   │   ├── adherenceService.ts
│   │   ├── ocrService.ts
│   │   ├── interactionService.ts
│   │   ├── emailService.ts
│   │   └── notificationService.ts
│   ├── repositories/
│   │   ├── medicationRepository.ts
│   │   ├── adherenceRepository.ts
│   │   └── familyRepository.ts
│   ├── utils/
│   │   ├── logger.ts
│   │   └── helpers.ts
│   ├── validations/
│   │   ├── medication.schema.ts
│   │   └── adherence.schema.ts
│   ├── types/
│   │   └── index.ts
│   ├── cron/
│   │   ├── reminderJob.ts
│   │   └── adherenceJob.ts
│   └── server.ts
├── prisma/
│   ├── schema.prisma
│   └── migrations/
├── .env.example
├── .env
├── tsconfig.json
├── package.json
└── pnpm-lock.yaml
```

---

## **Root Structure**
```
medicare-companion/
├── frontend/
├── backend/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── docs/
│   ├── uml/
│   └── design-patterns.md
├── .gitignore
├── README.md
└── pnpm-workspace.yaml