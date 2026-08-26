# Meta Ads Daily Streamlit Dashboard

Ready-to-deploy Streamlit project based on the supplied dashboard.

## What changed

- Meta Insights now uses `time_increment=1`, so campaign insights are returned day-by-day.
- `date_start` / `date_stop` are normalized as daily dates.
- New **Daily Overall Leads** section in Streamlit.
- Every calendar day in the selected range is shown, including zero-spend days.
- New **Download Daily Excel** button.
- Excel contains:
  - `Daily Report`: visual blocks in the requested format.
  - `Daily Table`: one row per day.
  - `Daily By Agent`: one row per day per media buyer.
- Excel respects the currently selected **Business Unit**.

## Daily report format

```text
1/8/2026
Overall Leads
Amount Spent: ...
Leads: ...
CPL: ...
```

## Deploy to GitHub + Streamlit Cloud

1. Create a new GitHub repository.
2. Upload the contents of this folder to the repository root.
3. Do **not** upload real secrets.
4. In Streamlit Cloud, create a new app from the repo.
5. Main file path: `app.py`.
6. Open **App settings -> Secrets** and add your real values using `.streamlit/secrets.toml.example` as a guide.
7. Deploy.

## Important

The app keeps its existing snapshot files under `app_data/`. On Streamlit Community Cloud, local disk is ephemeral and can reset when the app restarts/redeploys. This does not affect a fresh Meta refresh, but if permanent historical snapshot storage is required, use an external database/object store.
