# Design Guidelines: AI Sales Automation Platform

## Design Approach

**Selected Framework**: Design System Approach using **Linear + Notion** hybrid methodology

**Justification**: Enterprise SaaS productivity tool requiring information-dense layouts, data visualization, and professional credibility. Users need efficiency, scannable interfaces, and clear hierarchy for managing complex sales workflows.

**Key Design Principles**:
- Clean, professional aesthetics that inspire confidence
- Information density without clutter
- Scannable data tables and lists
- Clear visual hierarchy for action prioritization
- Dashboard-first thinking with data visualization

---

## Typography

**Font Family**: 
- Primary: Inter (via Google Fonts CDN)
- Monospace: JetBrains Mono (for email previews, code snippets)

**Hierarchy**:
- Page Headers: text-3xl font-semibold (Dashboard, Inbox, Leads, etc.)
- Section Headers: text-xl font-semibold
- Subsections: text-lg font-medium
- Body Text: text-base font-normal
- Metadata/Labels: text-sm font-medium
- Captions/Timestamps: text-xs font-normal
- Button Text: text-sm font-medium

---

## Layout System

**Spacing Primitives**: Use Tailwind units of **2, 3, 4, 6, 8, 12, 16, 20**
- Component padding: p-4, p-6
- Section spacing: space-y-6, space-y-8
- Card internal spacing: p-6
- Dashboard grid gaps: gap-6
- List item spacing: space-y-3
- Form field spacing: space-y-4

**Layout Structure**:
- Sidebar Navigation: Fixed left sidebar (w-64) with collapsible option
- Main Content Area: Full height with max-w-7xl container, px-8 py-6
- Dashboard Grid: 12-column system using Tailwind grid
- Two-column layouts: 2/3 main content + 1/3 sidebar for detail views

---

## Component Library

### Navigation
- **Top Bar**: Fixed header with search, notifications, user profile (h-16, border-b)
- **Sidebar**: Vertical navigation with icons + labels, active state highlighting, collapsible sections
- **Breadcrumbs**: For deep navigation (Dashboard > Leads > Contact Name)

### Dashboard Elements
- **Stat Cards**: Grid of 4 cards showing key metrics (deals closed, response rate, active leads, revenue)
  - Include trend indicators (↑ 12% from last month)
  - Icon + Number + Label layout
- **Activity Feed**: Timeline-style list with avatars, timestamps, action descriptions
- **Data Tables**: Sortable columns, row actions (view, edit, archive), pagination
  - Sticky headers for long tables
  - Alternating row subtle distinction for scannability

### Cards & Containers
- **Content Cards**: Rounded corners (rounded-lg), subtle border, p-6 padding
- **Email Preview Cards**: Show sender, subject, snippet, timestamp, AI draft indicator
- **Lead Cards**: Contact info, company logo placeholder, qualification score badge, quick actions

### Forms & Inputs
- **Text Inputs**: Consistent height (h-10), rounded-md, focus states with ring
- **Textareas**: For email drafts and playbook editing (min-h-32)
- **Select Dropdowns**: Custom styled with chevron icons
- **Toggle Switches**: For enabling/disabling automation rules
- **Rich Text Editor**: For sales playbook templates with formatting toolbar

### Buttons & Actions
- **Primary CTA**: Solid background, px-4 py-2, rounded-md, font-medium
- **Secondary**: Outline style with border
- **Tertiary**: Text-only with hover underline
- **Icon Buttons**: Square (w-10 h-10) for compact actions in tables/toolbars

### Data Visualization
- **Progress Bars**: For lead qualification scores (0-100)
- **Badges**: Status indicators (New Lead, Qualified, Contacted, Closed)
  - Small, rounded-full, px-2 py-1, text-xs
- **Tags**: For email categories, industries, deal stages

### AI-Specific Components
- **AI Draft Indicator**: Small badge showing "AI Generated" with sparkle icon
- **Playbook Template Card**: Editable template blocks with preview
- **Research Report Panel**: Collapsible sections with company data, news, insights
- **Qualification Score Display**: Circular progress indicator with percentage

### Overlays
- **Modal Dialogs**: Centered, max-w-2xl, with backdrop blur
- **Slide-over Panels**: Right-side panel (w-96) for email details, contact info
- **Dropdown Menus**: Context menus for table row actions
- **Toast Notifications**: Top-right positioned success/error messages

---

## Images

**Usage**:
- **No Hero Image**: This is a dashboard application, not a marketing site
- **Company Logos**: Placeholder circles (w-10 h-10) in lead cards and tables
- **Contact Avatars**: Small circles (w-8 h-8) in activity feed and email lists
- **Empty States**: Simple illustrations for "No leads yet" or "Inbox zero" states
- **Icons**: Use Heroicons (via CDN) for all interface icons - outline style for navigation, solid for badges/indicators

---

## Animations

**Minimal, Purposeful Motion**:
- Sidebar collapse/expand: transition-all duration-200
- Table row hover: subtle elevation change
- Modal fade-in: opacity transition
- **No scroll-triggered animations** - this is a productivity tool

---

## Key Screens Layout

**Dashboard**: 
- 4-column stat cards at top
- 2-column below: Activity feed (left 2/3) + Upcoming tasks (right 1/3)

**Inbox View**:
- 3-column layout: Email list (left 1/3) + Email preview (center 1/3) + AI actions panel (right 1/3)

**Leads Pipeline**:
- Kanban-style board with draggable cards OR table view toggle
- Filters sidebar on left, main content area

**Sales Playbook Editor**:
- 2-column: Template list (left 1/4) + Editor (right 3/4)