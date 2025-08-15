# SmartClean Stream

A Raspberry Pi-based RTSP to HLS streaming service with CORS support for cross-origin access.

## Features

- **RTSP to HLS Conversion**: Converts RTSP camera streams to HLS format using MediaMTX
- **Web Interface**: Clean, responsive web player for viewing streams
- **CORS Support**: Properly configured for cross-origin requests from other servers
- **Placeholder Content**: Fallback video when main stream is unavailable
- **ngrok Integration**: Secure tunneling for external access
- **Docker Deployment**: Easy containerized deployment
- **Auto-restart**: Systemd services for automatic startup

## Quick Start

### Prerequisites
- Raspberry Pi (or similar ARM-based Linux device)
- Docker and Docker Compose
- ngrok account and authtoken

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_NEW_REPO_NAME.git
   cd smartclean-stream
   ```

2. **Update configuration**
   - Edit `install.sh` and replace `YOUR_USERNAME` and `YOUR_NEW_REPO_NAME`
   - Update `NGROK_AUTHTOKEN` with your actual token

3. **Run installation**
   ```bash
   chmod +x install.sh
   ./install.sh
   ```

4. **Access your stream**
   - Local: http://localhost:8888
   - Remote: Check ngrok tunnel status

## Configuration

### Camera Stream
Update the RTSP source in `mediamtx.yml`:
```yaml
source: rtsp://username:password@camera-ip/stream
```

### Ports
- **8554**: RTSP (MediaMTX)
- **8888**: HTTP (Nginx web interface)
- **4040**: ngrok API (local)

## Architecture

```
RTSP Camera → MediaMTX → HLS Conversion → Nginx → Web Browser
                    ↓
              Placeholder Video
```

## License

[Add your license here]

## Contributing

[Add contribution guidelines here]
