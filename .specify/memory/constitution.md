<!--
SYNC IMPACT REPORT
==================
Version Change: UNVERSIONED → 1.0.0
Change Type: MAJOR (Initial ratification)

Modified Principles:
  - NEW: Code Quality
  - NEW: Testing Standards  
  - NEW: User Experience Consistency
  - NEW: Performance Requirements

Added Sections:
  - Core Principles (4 principles)
  - Performance Standards
  - Development Workflow
  - Governance

Removed Sections: None

Templates Consistency:
  ✅ spec-template.md - User scenarios align with UX consistency principle
  ✅ plan-template.md - Constitution Check section references this document
  ✅ tasks-template.md - Test tasks align with Testing Standards principle
  ✅ Command prompts - Generic guidance compatible with all principles

Follow-up TODOs: None - All placeholders resolved

Rationale for v1.0.0:
  Initial constitution ratification establishing four foundational principles
  for the renbrent.github.io portfolio site project. MAJOR version as this
  establishes the governance baseline.
-->

# Portfolio Site Constitution

## Core Principles

### I. Code Quality

All code MUST be maintainable, readable, and follow established patterns. This is NON-NEGOTIABLE.

**Rules**:
- Use consistent naming conventions (camelCase for JS, kebab-case for CSS/HTML)
- Maximum function/method length: 50 lines (exceptions require justification)
- Maximum file length: 500 lines (split into modules beyond this)
- Code MUST pass linting (ESLint, Prettier, or language-specific standards)
- No unused variables, imports, or dead code in production
- Comments required for: complex algorithms, business logic decisions, and "why" over "what"
- DRY principle: No copy-pasted code blocks (extract to reusable functions/components)

**Rationale**: Portfolio sites represent professional competence. Code quality directly reflects on credibility with recruiters and technical reviewers. Maintainability ensures the site remains updateable as career progresses.

---

### II. Testing Standards

All critical functionality MUST have automated tests. User-facing features require acceptance testing.

**Rules**:
- **Unit tests required for**: Utility functions, data transformations, validation logic
- **Integration tests required for**: Form submissions, API interactions, routing behavior
- **Visual regression tests required for**: Homepage, project showcase pages, responsive layouts
- **Acceptance tests required for**: Each user story in feature specifications (Given/When/Then scenarios)
- Test coverage target: 80% for utility code, 100% for critical paths (contact forms, navigation)
- Tests MUST run in CI/CD pipeline before deployment
- Broken tests block merges to main branch
- Test failures MUST be fixed before new features (no accumulation of technical debt)

**Rationale**: A broken portfolio site damages professional reputation. Automated testing prevents regressions when adding projects or updating content. Recruiters expect working functionality—failed demos lose opportunities.

---

### III. User Experience Consistency

The site MUST provide a cohesive, professional, and accessible experience across all pages and devices.

**Rules**:
- **Responsive design mandatory**: Mobile-first approach, test at 320px, 768px, 1024px, 1920px breakpoints
- **Accessibility (WCAG 2.1 AA)**: Semantic HTML, ARIA labels, keyboard navigation, color contrast ratios ≥4.5:1
- **Consistent branding**: Single color palette, typography system (max 2 font families), unified spacing scale
- **Navigation**: Same header/footer across all pages, clear active state indicators, breadcrumbs for deep pages
- **Loading states**: Skeleton screens or spinners for async content, no layout shifts (CLS score <0.1)
- **Error handling**: Friendly error messages (no stack traces), clear recovery actions, maintain layout
- **Content structure**: Consistent heading hierarchy (h1 → h2 → h3), predictable page layouts
- **Browser support**: Last 2 versions of Chrome, Firefox, Safari, Edge (test in all)

**Rationale**: Inconsistent UX signals carelessness and harms professional brand. Recruiters browse on various devices and expect smooth experiences. Accessibility is both ethical and legally important for public-facing sites.

---

### IV. Performance Requirements

The site MUST load quickly and perform smoothly to maintain professional perception.

**Rules**:
- **Core Web Vitals targets** (Google Lighthouse, measured on 3G network):
  - LCP (Largest Contentful Paint): <2.5s
  - FID (First Input Delay): <100ms
  - CLS (Cumulative Layout Shift): <0.1
- **Lighthouse scores**: Performance ≥90, Accessibility ≥95, Best Practices ≥95, SEO ≥95
- **Asset optimization**:
  - Images: WebP format with fallbacks, lazy loading for below-fold, max 200KB per image
  - JavaScript: Code splitting, async/defer loading, tree shaking, minification
  - CSS: Critical CSS inlined, non-critical deferred, minification, removal of unused styles
  - Fonts: WOFF2 format, font-display: swap, preload critical fonts
- **Bundle size limits**:
  - Initial JS bundle: <100KB gzipped
  - Initial CSS bundle: <50KB gzipped
  - Total page weight (first load): <500KB
- **Caching strategy**: Aggressive caching for static assets (1 year), versioned filenames for cache busting
- **Monitoring**: Track performance metrics in production, alert on regressions >10%

**Rationale**: Slow sites lose visitors within 3 seconds. Recruiters have limited patience—poor performance suggests lack of modern web development skills. Google penalizes slow sites in search rankings, reducing discoverability.

---

## Performance Standards

Performance is measured and enforced at every stage:

1. **Development**: Local Lighthouse audits before committing changes
2. **CI/CD**: Automated performance budgets in GitHub Actions (fails builds exceeding limits)
3. **Deployment**: Post-deployment verification of Core Web Vitals in production
4. **Monitoring**: Weekly performance audits, quarterly optimization reviews

**Performance budget enforcement**:
- Budget file tracked in repository (`.github/performance-budget.json`)
- Automated alerts for budget violations
- Violations require optimization before merge approval

---

## Development Workflow

All feature development follows the SpecKit specification-driven workflow:

1. **Specification**: Create detailed spec with user stories and acceptance criteria (`/speckit.specify`)
2. **Planning**: Generate implementation plan with technical context (`/speckit.plan`)
3. **Tasks**: Break down work into prioritized, testable tasks (`/speckit.tasks`)
4. **Implementation**: Execute tasks with test-first approach when tests required (`/speckit.implement`)
5. **Validation**: Verify against acceptance criteria and constitution compliance (`/speckit.analyze`)
6. **Review**: Code review checks constitution compliance before merge

**Branch strategy**:
- Main branch: Production-ready, protected, requires PR approval
- Feature branches: `###-feature-name` format (e.g., `001-portfolio-site`)
- Commits: Conventional commit format (`feat:`, `fix:`, `docs:`, `perf:`, `test:`, `refactor:`)

**Merge requirements**:
- All tests passing (CI/CD green)
- Lighthouse scores meet thresholds
- Code review approved
- No merge conflicts
- Constitution compliance verified

---

## Governance

**Authority**: This constitution supersedes all other practices and preferences. When in doubt, constitution rules win.

**Amendment Process**:
- Amendments require clear justification documenting why current principles are insufficient
- Version increments follow semantic versioning:
  - **MAJOR**: Principle removal or backward-incompatible governance changes
  - **MINOR**: New principles added or materially expanded guidance
  - **PATCH**: Clarifications, wording improvements, non-semantic refinements
- Amendments tracked with updated ratification dates and version history
- All dependent templates and documentation MUST be updated to reflect amendments

**Compliance Verification**:
- All PRs MUST include constitution compliance checklist (use `/speckit.checklist`)
- Reviewers MUST verify alignment with principles before approval
- Violations MUST be corrected before merge (no exceptions)
- Complexity or deviations MUST be justified in writing and linked to spec documents

**Living Document**: This constitution evolves with the project. Periodic reviews (quarterly) assess whether principles remain appropriate for project stage and goals.

---

**Version**: 1.0.0 | **Ratified**: 2026-01-15 | **Last Amended**: 2026-01-15
