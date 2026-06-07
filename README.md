# openhive-test

This repository is the primary testing ground for OpenHive, an AI agent swarm that maintains open source repositories. It exists so the OpenHive agents can be exercised against real GitHub events and their behaviour verified from end to end.

## What was verified here

OpenHive watches this repository and responds to real activity. The Triage Agent classified new issues and posted the kind of clarifying questions a senior engineer would ask. The PR Review Agent reviewed pull requests and caught a description that claimed test coverage the diff did not actually contain. The Security Agent scanned a dependency file, found known vulnerabilities in the OSV database, and opened a patch pull request rather than only raising a flag. The Health Agent produced a repository health score, and the daily digest folded every finding into a single plain language report.

## How it works

A GitHub webhook forwards events from this repository to the OpenHive backend. The backend routes each event through a LangGraph agent graph, calls Claude for the reasoning, records every verdict in Supabase before any GitHub write happens, and posts the result back here as a comment, a label, or a patch pull request.

## Learn more

The full OpenHive project, including the source code, the installation guide, and the live dashboard, lives at https://github.com/yerramsettysuchita/openhive
