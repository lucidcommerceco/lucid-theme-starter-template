# Blank repo for moving themes from the Shopify Theme Store into GitHub

## Overall principles

1. Main branch is titled `published` and should be published as the live theme
2. There is a `staging` branch, which you can choose to add to the store if you work on a staging theme with clients
3. There is a `theme-store-theme` branch, which you should use to pull down the latest versions of the Theme Store theme whenever updates are released. This should always reflect the code in the Theme Store version of the theme with no changes. Before merging, you can cherry-pick updates into a branch off the `staging` branch.

## How to use

1. Create a new repo using this template. Be sure to select the option to **include all branches**.
2. Clone to your local dev environment
3. Update the `shopify.theme.toml` file to set `store` to the Shopify subdomain of your store. This will enable you to run the Shopify CLI like this: `shopify theme dev -e main`. If you want to use this theme on multiple stores, you can add additional environments like `[environments.ca]` (for Canada, say) with the `store` set to the subdomain of the Canadian store.
4. Switch to the `theme-store-theme` branch and run `shopify theme pull -e main -t 123456789` where 123456789 is the id of the latest unchanged Theme Store theme you are working on.
5. If this is the first time you are setting this up, merge `theme-store-theme` into `staging`.
6. You can work directly in `staging` if the theme isn’t yet published. Or, you can create a branch of `staging` with a name that reflects the current sprint.
7. Work locally and commit frequently.
8. Push when you want to show `staging` to clients.
9. Merge into `published` when tested and ready to deploy live.
10. What did I miss? Feel free to submit issues.
