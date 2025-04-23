# Technical Decisions

## Brief

We want to document a FAQ of sorts around the technical decisions made, and rationale for these.

## Decisions

### Chat Platforms

We chose Telegram because the API is open, it is relatively easy to build for, and GeeksHacking community is on Telegram, and therefore can serve as a first user.

We do intend to extend this to other platforms as much as time and cost will allow.

### Chat Group Linking OTP

Although the Dashboard uses a more secure authentication method, we decided on an OTP-based linking flow for simplicity.

While a social login might be more secure and easier for access, we do not think the initial setup will be repeated frequently.

The OTP is valid for 10 minutes, after which it automatically expires. We think this will be sufficiently secure for our purposes.
