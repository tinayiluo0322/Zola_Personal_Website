[![pipeline status](https://gitlab.com/ly178/tinayiluo_ids721_week1/badges/main/pipeline.svg)](https://gitlab.com/ly178/tinayiluo_ids721_week1/-/commits/main)

# Luopeiwen (Tina) Yi's Portfolio Web App 

## Goal
Create my personal website with Zola hosted on Vercel with Gitlab workflow for build and deployment. 

## Preparation
1. Install Zola 
2. Create website with `zola init`
3. Add a theme for css `cd themes` then `git submodule add <theme name (Kita)>`
4. Create pages in the `content` folder 
5. `zola serve` to test website or `zola build`
6. Install Vercel CLI 
7. Login to Vercel with `vercel login`
8. Link repo with `vercel link`
9. Copy Vercel token, Vercel team id, and Vercel Org id to Gitlab secrets 
10. Push repo to run pipeline filr `.gitlab-ci.yml`

## Personal Website

1. Introduction
2. About
3. Main Content
- Awards
- Skills
- Professional Experience
- Projects
- Research
- Education

## Web App Delivery 

[Luopeiwen (Tina) Yi's Personal Webiste](https://tinaportfolio.vercel.app/)