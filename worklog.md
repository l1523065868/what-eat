---
Task ID: 1
Agent: Main Agent
Task: Fix webpage not displaying, verify email login & admin review features, add admin panel UI

Work Log:
- Diagnosed that the Next.js dev server process was not running (killed after previous session ended)
- Restarted the dev server using detached process spawn
- Verified all API endpoints return 200: /, /api/provinces, /api/rankings, /api/posts, /api/admin/posts, /api/admin/reviews
- Confirmed email login is fully implemented: login-modal.tsx uses email, API /api/auth/login uses email, User model has email field with @unique
- Confirmed post moderation is implemented: Post model has status field (pending/approved/rejected), /api/posts GET filters by status=approved, POST creates with status=pending
- Created AdminPanel component at src/components/admin-panel.tsx with tabs for pending/approved/rejected posts and pending reviews
- Added 'admin' tab to navigation bar and store type
- Updated page.tsx to render AdminPanel for 'admin' tab
- All lint checks pass

Stage Summary:
- Dev server running and all pages/APIs accessible
- Email login fully functional
- Post moderation system fully functional with admin review panel
- Admin panel allows reviewing posts and reviews with approve/reject actions
- 10 seed posts already in 'approved' status, new user posts default to 'pending'
