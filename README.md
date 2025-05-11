# GetInData-Project
A project for UB classes under GetInData.

Authors: Jan Szczepanek, Maciek Kasztelaniec, Karol Rochalski

## When Should the Churn Model Be Used?
B2C = every month ideally around 10 days before renewal (to have time to target such customers, while). Short emotional decisions leave big risks on churn. We need fast rapid scoring to have time to target potential churning customers
B2B = quaterly and then monthly (starting 90 days before renewal). It focuses long term health, reduces risk and allows sales to renew contract

## How often should such model be retrained?
Every 6 months with evaluation, but we also monitor prediction performance metrics which could trigger early full retrain

## Pipeline steps
1. raw data ETL
2. feature engeneering
3. churn model (LightGBM)
4. explainability
5. churn results
6. model output
7. uplift model (Xlearners)
8. Model delivery

## raw data for B2B
accounts - basic account raw data
products - list of all products
subscriptions - contract-level details
account_product_subscriptions - product/account maping table
product_usage_events - raw event-level usage data across products
api_usage_logs - api call-level logs
support_tickets - account support interactions
billing_invoices - invoice records
payments - payment transactions
nps_responses - net promoter score survey responses

## raw data for B2C
raw_user_settings - basic user setting info
raw_users - basic profile info
raw_products - list of all products
raw_subscriptions - contract-level details
raw_user_product_subscriptions - product/account maping table
raw_product_usage_events - raw event-level usage data across products
raw_api_usage_logs - api call-level logs
raw_support_tickets - account support interactions
raw_billing_invoices - invoice records
raw_payments - payment transactions
raw_nps_responses - net promoter score survey responses

## base tables
base_accounts - b2b account informations
base_users - b2c users informations
base_subscriptions - account/user subscriptions
base_product_usage_events - account/user product actions with timestamps
base_api_usage_logs - account/user api usage with timestamps
base_payments - invocie records with transcation information
base_support_tickets - account/user support ticket issuing
base_nps_responses - account/user nps responses
base_product_catalog - metadata for all available products

## intermediate tables
intermediate_account_usage - b2b usage trend, volatilty, recency and frequency metrics
intermediate_user_usage - b2c usage trend, volatilty, recency and frequency metrics
intermediate_subscriptions - table with all subscription details, number of days till finish
intermediate_payment_behavior_metrics - user/account metrics like days late, missed payments
intermediate_experience - user/account metrics: ticket per quarter, resolution time, satisfaction, nps

## master tables
master_churn_features_b2b
master_churn_features_b2c

## Data Delivery
Business Intelligence Visualization
Data Storytelling-driven Presentation
Dynamic Visualizations

## Model Delivery
Remote hosting
Container access
