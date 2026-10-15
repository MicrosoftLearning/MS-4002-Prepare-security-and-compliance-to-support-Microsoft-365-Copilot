# MS-4002: Prepare security and compliance to support Microsoft 365 Copilot

This repo contains exercises and supporting files for [MS-4002: Prepare security and compliance to support Microsoft 365 Copilot](https://learn.microsoft.com/training/courses/ms-4002).

The exercises may be used in both self-paced skilling experiences on [Microsoft Learn](https://learn.microsoft.com) and in Microsoft authorized instructor-led training.

## Course website

The exercises are published using the same [Microsoft Learning Jekyll theme](https://github.com/MicrosoftLearning/Jekyll-Theme) as the AZ-104 course.

[Open the course exercises](https://sayedimac.github.io/MS-4002-Prepare-security-and-compliance-to-support-Microsoft-365-Copilot/).

### Publish to GitHub Pages

1. In this repository's **Settings > Pages**, select **GitHub Actions** as the build and deployment source.
2. Merge the website changes into `master`. The **Deploy course to GitHub Pages** workflow builds the site and deploys it to the `github-pages` environment. You can also run it manually from **Actions**, selecting `master`.
3. Wait for the deployment to finish, then open the course website linked above. If the `github-pages` environment requires approval, approve the deployment.

Pull requests targeting `master` build the site without deploying it. The workflow uses GitHub's supported Jekyll builder; no custom credentials or Azure pipeline are required. The existing `_build.yml` packages lab content separately and is not used for the website.

Exercise files belong in `Instructions/Labs/` and must include `lab.title` in their YAML front matter to appear in the course index. The site applies the exercise layout automatically. Keep images and other supporting files alongside the exercises.

## Information for MCTs
<!-- You can remove this section if the exercises will not be used to support Microsoft Official Curriculum ILT -->

**Are you an MCT?** - Have a look at our [GitHub User Guide for MCTs](https://microsoftlearning.github.io/MCT-User-Guide/)

Any MCT (Microsoft Certified Trainer) can submit a pull request to the code or content in the GitHub repro. Microsoft and the course author will then triage and include content and lab code changes as needed. You can submit bugs, changes, improvement, and ideas. Find a new Azure or Microsoft 365 feature before we have? Submit a new demo!
