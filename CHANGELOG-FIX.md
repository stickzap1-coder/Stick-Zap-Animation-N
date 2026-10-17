# Update notes

## Button responsiveness / startup fix
The app previously waited for browser IndexedDB and project-list loading before attaching its UI event handlers. If that initialization stalled, buttons could appear unresponsive. This update attaches handlers first, starts with a temporary project, then loads saved data and updates the UI. If saved-project loading fails, the app continues with a fresh in-memory project rather than blocking all controls.

The existing `gemini-3.8-flash` model identifier is documented by Google's current Gemini API model list. This update does not change model selection because a model failure would not explain the local-only Quick local outline button failing to respond.
