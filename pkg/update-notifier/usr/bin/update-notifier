#!/usr/bin/env bash
# Configuration
MAX_DAYS=3
STATE_FILE="$HOME/.local/share/update-notifier/last_update"

mkdir -p "$(dirname "$STATE_FILE")"

if [[ ! -f "$STATE_FILE" ]]; then
    notify-send "System Update Reminder" "You haven't run a full system update yet."
    exit 0
fi

last_epoch=$(date -d "$(cat "$STATE_FILE")" +%s)
current_epoch=$(date +%s)
day_difference=$(( (current_epoch - last_epoch) / 86400 ))

if (( day_difference >= MAX_DAYS )); then
    notify-send "System Update Reminder" "It’s been $day_difference days since the last system update."
fi
