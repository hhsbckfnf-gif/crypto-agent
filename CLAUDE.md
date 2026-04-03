# CLAUDE.md - AI Agent Context

This file provides AI assistants with critical context about the Crypto Trading Agent project.

## Project Overview

**Crypto Trading Agent** is a production-grade cryptocurrency futures trading system that combines:
- Rule-based technical analysis (RSI, moving averages)
- Optional AI-powered decision making
- Rigorous risk engine for position validation
- Paper trading simulator for backtesting
- Web UI for monitoring and control

The system is designed with safety as the top priority.

## CRITICAL RULES

These rules are non-negotiable and override all other considerations:

1. **PAPER_TRADING=true and LIVE_TRADING=false by default**
   - Never enable live trading automatically
   - Live trading requires explicit user approval after validation

2. **Risk Engine is the AUTHORITY**
   - Agent proposes (suggests action + confidence)
    - Risk engine decides (validates against all checks)
   - Final execution only if ALL checks pass

3. **Safety First Principles**
   - NO martingale strategies (never increase position to recover losses)
   - NO averaging down (never add to losing positions)
   - NO revenge trading (emotions cause losses)
   - If uncertain -> DO NOTHING (HOLD action)
