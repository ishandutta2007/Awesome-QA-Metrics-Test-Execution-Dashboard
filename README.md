# Awesome-QA-Metrics-Test-Execution-Dashboard

# Awesome QA Metrics & Test Execution Dashboard

> A curated list of top QA Metrics and Test Execution Dashboard platforms — both SaaS/Hosted commercial test analytics solutions and open-source alternatives for visualizing test results, tracking flakiness, and measuring release readiness.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Katalon TestOps](#katalon-testops)
  - [LambdaTest Analytics](#lambdatest-analytics)
  - [Zephyr Scale](#zephyr-scale)
  - [Cypress Cloud](#cypress-cloud)
  - [Sauce Labs Insights](#sauce-labs-insights)
- [Open-Source Software](#-open-source-software)
  - [ReportPortal](#reportportal)
  - [Allure TestOps](#allure-testops)
  - [test-reporting](#test-reporting)
  - [Helios](#helios)
  - [Allure Report](#allure-report)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted QA Metrics and Test Execution Dashboard platforms. These are not open-source but are included as reference points for feature comparison.

### Katalon TestOps
**Type:** Test analytics with custom dashboards and seven core reports
Katalon TestOps provides a dashboard module with **seven reports** covering test activities, release readiness, productivity, quality (flakiness distribution), platform coverage, requirement coverage (Jira and BDD), and local test environments [citation:4]. The January 2026 release added **custom dashboard creation**, allowing teams to curate project-scoped dashboards with widgets from a Widget Library, tailored for sprints, teams, or specific stakeholders without exporting data or stitching reports in spreadsheets [citation:10]. Platform Coverage requires the Ultimate plan [citation:4].
**Best for:** Teams already using Katalon for test automation wanting integrated analytics with customizable stakeholder-specific dashboards.

### LambdaTest Analytics
**Type:** Project analytics with executive-ready insights
LambdaTest's Project Analytics Dashboard is positioned as a strategic asset for both QA teams and C-Suite executives, consolidating key metrics into a single interactive view [citation:7]. Key widgets include **Testing Velocity** (total tests executed, average daily velocity), **Testing Distribution** (browser and device coverage), **Test Case Quality Trends** (pass/fail/anomaly rates), and **Projects Health** cards with color-coded risk indicators [citation:7]. An **Executive View** provides high-level summaries for board presentations, with export and share capabilities.
**Best for:** Organizations needing to communicate QA metrics to leadership with executive-focused dashboards and exportable reports.

### Zephyr Scale
**Type:** Jira-native test execution reporting
Zephyr Scale's Test Execution Results (Summary) report provides a daily overview of test progress, including overall progress (completed vs. pending executions), pass/fail/not-run ratios, and actual vs. estimated execution effort [citation:5][citation:11]. Reports can be filtered by projects, epics, stories, versions, or date ranges, with PDF export and raw data export to Excel for stakeholder sharing [citation:5]. This makes it the natural choice for teams already running tests inside Jira.
**Best for:** Jira-centric teams wanting test progress reporting without leaving their existing Atlassian ecosystem.

### Cypress Cloud
**Type:** Test analytics for Cypress projects
Cypress Cloud provides run trends, test suite size, and flake rates, with **Enterprise Reporting** spanning across projects to spot patterns and ensure consistency. The Data Extract API allows retrieval of aggregate and raw test data for external analytics systems. Focused on Cypress test suites only.

### Sauce Labs Insights
**Type:** Test analytics with failure history and trend tracking
Sauce Labs provides test analytics tracking failure history across runs, alongside its real device cloud. Its Job Performance Analysis page shows execution history for individual jobs with pass/fail rates, error rates, and duration trends.

---

## 🟩 Open-Source Software

Self-hosted, community-driven QA Metrics and Test Execution Dashboard tools. The open-source ecosystem is anchored by **ReportPortal** and **Allure** as the two leading platforms.

### ReportPortal
**Stack:** Java / PostgreSQL / OpenSearch | **License:** Apache-2.0
ReportPortal is a TestOps service for collecting, analyzing, and visualizing automated test results in real time, distributed under Apache 2.0 and free for commercial use (with two paid premium features: Quality Gates and SCIM Server) [citation:2][citation:8]. Key dashboard capabilities include:
- **Real-time results** with integration into Jenkins, Jira, BDD, and major testing frameworks [citation:8]
- **Automatic Analysis** using ML-based defect triage to flag root causes and highlight which results need human review [citation:8][citation:14]
- **Collaborative triage** classifying failures as Product Bug, Automation Bug, System Issue, No Defect, or To Investigate [citation:2]
- **Historical data** and trend analysis across executions [citation:8]
- **Widgets and dashboards** including Overall statistics, Unique bugs table, and Passing rate summary [citation:8]
- **1700+ companies** and **40+ Fortune 500** companies using it, with **85M+ launches/year** [citation:14]

Deploys via Docker Compose with PostgreSQL [citation:2]. **Trade-off:** The full stack requires meaningful resources (2 CPUs, 6 GB RAM, 20 GB disk minimum) [citation:2].
**Best for:** Teams wanting a proven, actively maintained open-source TestOps dashboard with ML-based failure triage and strong framework integration.

### Allure TestOps
**Stack:** Java / (Check repository) | **License:** Open Source (core) / Commercial
Allure TestOps is an actionable reporting platform and test management system built on the open-source **Allure Report** standard, uniting automated and manual tests in one workspace [citation:3]. Dashboard and analytics capabilities include **instant status evaluation**, **long-term historical trend analysis**, **automatic failure grouping**, **known-issue detection**, and **flaky test detection** [citation:3]. Complete context for root cause analysis includes history, environment, attachments, full logs, and CI/CD metadata [citation:3]. The open-source Allure Report is Apache 2.0; Allure TestOps itself is commercial with a self-hosted option [citation:3]. An MCP server is available for AI agent access to test cases, launches, and analytics [citation:15].
**Best for:** Teams already using Allure Report wanting to upgrade to centralized storage, historical analytics, and test management without abandoning the open standard.

### test-reporting
**Stack:** Python / SQLite | **License:** Open Source (PyPI)
test-reporting is a multi-project test reporting dashboard for Playwright/Pytest with shared database support [citation:6]. Key features include:
- **Projects landing page** with health scores and quick metrics
- **Overview dashboard** with module breakdown, failure hotspots, quality trends, flaky tests, and performance metrics
- **Run details** with test-by-test breakdown, screenshots, traces, error messages, and logs
- **Test history** with search, filter, trend analysis, and run comparison
- **Multi-project support** with a single shared SQLite database, concurrent-safe via WAL mode

Setup is minimal: add a plugin to `conftest.py`, create `reporting.ini`, run tests, then `test-report generate` and `test-report open` [citation:6].
**Best for:** Playwright/Pytest teams wanting a lightweight, self-hosted reporting dashboard with multi-project support and minimal setup, accepting a Python/SQLite scope.

### Helios
**Stack:** Rust / React / GitHub Actions | **License:** MIT
Helios is an interactive CI/CD dashboard for GitHub Actions providing deployment management, test analytics, and release management [citation:12]. Key test analytics features include:
- **Test Insights**: ingests JUnit XML reports to drill into individual test suites and cases with pass/fail, error messages, and log snippets
- **Flaky test tracking** across branches over time
- **Unified Dashboard**: branches, PRs, builds, test suites, and deployments in one canvas
- **Release Management**: draft, review, and publish release candidates with auto-generated release notes and tagging

It locks chosen environments to prevent collisions and displays live progress until tests finish or timeout [citation:12].
**Best for:** Teams using GitHub Actions wanting a unified CI/CD and test analytics dashboard with deployment and release management in one tool.

### Allure Report
**Stack:** Java / JavaScript | **License:** Apache-2.0
Allure Report is the foundational open-source framework-agnostic test result visualization tool that transforms test execution data into interactive HTML reports [citation:9]. It works with **30+ testing frameworks** across JavaScript, Python, Java, C#, PHP, and Ruby, integrating with Jenkins, GitHub Actions, Azure DevOps, and JetBrains IDEs [citation:9]. **Limitation:** It generates standalone HTML reports per run rather than a centralized dashboard with historical aggregation—Allure TestOps is the path to centralized analytics [citation:3].
**Best for:** Teams wanting a proven, framework-agnostic reporting standard that generates rich static HTML reports without a server, or as a stepping stone to Allure TestOps.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Historical Trends | Flaky Detection | ML/AI Triage | Self-Hosted | Best For |
|----------|---------|-------|-------------------|-----------------|--------------|-------------|----------|
| **Katalon TestOps** | Proprietary | Cloud | ✅ 7 reports | ✅ Flakiness distribution | (Custom dashboards) | ❌ | Katalon users + custom dashboards |
| **LambdaTest** | Proprietary | Cloud | ✅ Executive view | (Quality trends) | ❌ | ❌ | C-Suite reporting |
| **Zephyr Scale** | Proprietary | Jira plugin | ✅ Execution summary | (Check) | ❌ | ❌ | Jira-native test progress |
| **ReportPortal** | Apache-2.0 | Java/Postgres | ✅ Rich widgets | ✅ | ✅ ML Auto-Analyzer | ✅ | Proven OSS TestOps dashboard |
| **Allure TestOps** | Open core / Commercial | Java | ✅ Deep history | ✅ | ✅ Failure grouping | (Self-hosted option) | Allure Report upgraders |
| **test-reporting** | Open Source | Python/SQLite | ✅ Trend analysis | ✅ | ❌ | ✅ | Playwright/Pytest lightweight |
| **Helios** | MIT | Rust/React | ✅ Branch tracking | ✅ | ❌ | ✅ | GitHub Actions unified dashboard |
| **Allure Report** | Apache-2.0 | Java/JS | ❌ (Per-run) | ❌ | ❌ | ✅ (Static) | Framework-agnostic static reports |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source QA Metrics or Test Execution Dashboard tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem is anchored by **ReportPortal** (proven TestOps dashboard with ML-based triage, 1700+ companies) and **Allure** (the open reporting standard, with TestOps as the centralized upgrade path) [citation:2][citation:3][citation:14]. For lightweight Playwright/Pytest reporting, **test-reporting** offers a minimal setup with multi-project support [citation:6], while **Helios** uniquely combines CI/CD deployment management with test analytics for GitHub Actions teams [citation:12]. Commercial platforms like Katalon TestOps and LambdaTest remain differentiated by executive-focused dashboards and stakeholder-specific customization [citation:7][citation:10].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
