# The Commons Event Creator

A streamlined event creation system for The Commons, built on top of Luma's API. This tool helps members create events while automatically checking for room conflicts and managing host permissions.

## Features

- 🗓️ Create events with automatic conflict detection
- 🏠 Visual room selection with interactive map
- 👥 Automatic host verification and co-host addition
- 🕒 Smart default time suggestions
- 🔄 Real-time conflict checking
- 🎨 Beautiful, user-friendly interface

## For Administrators

### Room Configuration

To update available rooms and buildings:

1. Navigate to `config/rooms.json`
2. Edit the JSON file structure:
   ```json
   {
     "buildings": {
       "540": {
         "address": "540 Laguna St, San Francisco, CA 94102",
         "rooms": [
           {
             "id": "hogwarts",
             "name": "Hogwarts Hall",
             "description": "Main event space"
           },
           // Add more rooms here...
         ]
       }
     }
   }
   ```
3. Save the file - changes will be reflected immediately

### Updating the Map

To update the Commons map:

1. Replace the file at `static/images/commons_map.png`
2. Make sure the new image:
   - Is in PNG format
   - Has a clear layout of all rooms
   - Is optimized for web (recommended size: 1000-1500px wide)
   - Has good contrast for readability

### Environment Configuration

Create a `.env` file with:
```bash
LUMA_API_KEY=your_api_key_here
LUMA_API_BASE_URL=https://api.lu.ma/public/v1
DEBUG_MODE=false
DEFAULT_BUFFER_MINUTES=0
```

## For Developers

### Setup

1. Clone the repository
2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up environment variables (see above)
5. Run the application:
   ```bash
   python main.py
   ```

### Testing

Run tests with:
```bash
python -m pytest
```

## Future Features & Improvements

Here are some exciting potential features for future development:

### Integration Possibilities
- 🤖 Slack Integration
  - Allow event creation directly from Slack
  - Send notifications about new events
  - Room booking commands
- 📱 Mobile App Integration
  - Native mobile experience
  - Push notifications
- 📧 Email Notifications
  - Custom email templates
  - Calendar invites

### Feature Enhancements
- 🔄 Recurring Events
  - Support for weekly/monthly events
  - Series management
- 🎨 Room Layouts
  - Interactive room setup options
  - Capacity tracking
- 📊 Analytics Dashboard
  - Usage statistics
  - Popular time slots
  - Room utilization

### User Experience
- 🌙 Dark Mode
- 🌐 Multi-language Support
- 📱 Responsive Design Improvements
- 🎟️ Waitlist Management

## Contributing

We welcome contributions! Please see our contributing guidelines for more details.

## To Do

* add ability to set a nonstandard location (e.g. event for commons people that is not actually at the commons)
* add support for automatically submitting Luma events to the Commons Luma calendar if someone's added the commons gmail as a cohost but forgot to submit the event to the luma calendar
* [just for Ruth's parent circle for now to pilot] add support for converting an event into a recurring event (maybe with a cron job to automatically make future events) at most 3 months in advance
  * add support for removing or updating recurring events

## Support

Need help? Reach out on [Slack](https://thesfcommons.slack.com/archives/C08BGQEM3NG)

## License

This project is proprietary and for use by The Commons only.
