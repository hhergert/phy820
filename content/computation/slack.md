---
title: "Slack"
date: 2020-09-01T18:35:37-04:00
weight: 1
draft: false
---

## Installation

You can access the Slack channel of the course through the link in the sidebar, or through the link in the invitation mail that you received at the beginning of the course. It is recommended that you install the Slack **desktop client**, which is available for all major platforms -- usually, a dialog prompt appears when you connect to the Slack channel through your browser.

## Math Rendering

Please install the math rendering extension for the Slack desktop client. This will allow you to type equations and symbols using **LaTeX** syntax (via the MathJax library). 

{{%notice note%}}
You will need a working Python installation to install this extension. The installation script was tested with **Python 3.8** and **Slack 4.8.0**.
{{% /notice %}}


Either 

* download (or clone it) from [Github](https://github.com/thisiscam/math-with-slack), or 

* obtain it by cloning the distribution repository for the course (see sidebar). After cloning (or updating), navigate to the appropriate subfolder and install it by executing the following commands (either on the command line or in your Anaconda terminal):

```bash
cd path-to-your-local-copy-of-repo/apps/math-with-slack
sudo python math-with-slack.py
```

### Screenshots:

![Syntax](../slack_math_a.png?width=50pc)
![Rendered](../slack_math_b.png?width=50pc)
