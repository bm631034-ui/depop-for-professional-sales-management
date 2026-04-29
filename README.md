# Depop Sales Manager

A comprehensive React Native mobile application for managing Depop sales with advanced features including screenshot OCR data extraction, financial tracking, and bulk image uploads to multiple platforms.

## Features

### 📸 Screenshot Data Extraction
- **AI-Powered OCR**: Automatically extract text from purchase receipts and screenshots using Tesseract.js
- **Smart Data Recognition**: Identifies item names, prices, dates, and seller information
- **One-Tap Processing**: Simply take a screenshot or upload an image to auto-populate data

### 💰 Revenue Tracker (Accountant-Style Spreadsheet)
- **Master Revenue Sheet**: Track all sales with complete financial data
- **Auto-Calculated Metrics**:
  - Profit per item
  - Profit margins
  - Gross vs. net revenue
  - Platform fees automatically deducted
- **Financial Categories**:
  - Gross Revenue & Net Revenue (after fees)
  - Cost of Goods Sold (COGS)
  - Packaging & Shipping Costs
  - Platform Fees
  - Profit Analysis
- **Filtering & Sorting**: By date, platform, category, profit
- **Data Export**: Generate financial reports

### 📤 Bulk Image Upload
- **Multi-Platform Support**: Upload to Depop, Vinted, and eBay simultaneously
- **Batch Processing**: Add multiple items and upload all at once
- **Platform-Specific Details**:
  - Item title & description
  - Pricing & shipping costs
  - Item condition
  - Category selection
  - Multiple images per item
- **Upload Status Tracking**: Real-time progress updates

### 🧮 Integrated Calculator
- **Advanced Financial Calculations**:
  - Profit margin calculator
  - Break-even analysis
  - Platform fee deductions
  - ROI calculations
  - Tax estimates
- **Quick Reference**: Built-in financial formulas

### 📊 Dashboard Analytics
- **Key Metrics Overview**:
  - Total revenue
  - Total profit
  - Average item profit
  - Profit margins
  - Items sold count
- **Platform Performance**: Sales distribution across platforms
- **Trend Analysis**: Monthly revenue trends
- **Category Breakdown**: Profit by item category

### 🔍 Financial Management Suite
- **Accountant-Ready Reports**: Professional financial summaries
- **Tax Calculations**: Estimated tax liability
- **Performance Metrics**: ROI, conversion rates, average selling prices
- **Time-Based Analytics**: Daily, weekly, monthly, yearly reports

### 🛍️ Sourcing Tab (Coming Soon)
- Inventory management
- Supplier tracking
- Cost analysis

## Project Structure

```
depop-sales-manager/
├── src/
│   ├── screens/                    # Main app screens
│   │   ├── DashboardScreen.tsx    # Financial overview
│   │   ├── RevenueTrackerScreen.tsx # Spreadsheet data
│   │   ├── BulkUploadScreen.tsx   # Multi-platform upload
│   │   └── CalculatorScreen.tsx   # Financial calculator
│   ├── components/                # Reusable components
│   │   ├── ScreenshotExtractor.tsx # OCR image processor
│   │   ├── SpreadsheetViewer.tsx  # Data table view
│   │   ├── CalculatorWidget.tsx   # Mini calculator
│   │   └── BulkUploadForm.tsx     # Upload form
│   ├── services/                  # Business logic
│   │   ├── OCRService.ts          # Tesseract OCR
│   │   ├── DatabaseService.ts     # SQLite operations
│   │   ├── ImageUploadService.ts  # Platform API calls
│   │   └── FinanceService.ts      # Financial calculations
│   ├── store/                     # Redux state management
│   │   ├── slices/
│   │   │   ├── revenueSlice.ts
│   │   │   ├── uploadSlice.ts
│   │   │   └── calculatorSlice.ts
│   │   └── index.ts
│   ├── utils/                     # Helper functions
│   │   ├── financialHelpers.ts    # Accounting formulas
│   │   ├── dataValidation.ts      # Input validation
│   │   └── platformIntegration.ts # Platform configs
│   └── App.tsx                    # Root component
├── assets/                        # App icons & images
├── app.json                       # Expo configuration
├── package.json                   # Dependencies
├── tsconfig.json                  # TypeScript config
├── .env.example                   # Environment template
└── README.md                      # This file
```

## Technology Stack

| Technology | Purpose |
|-----------|---------|
| **React Native** | Cross-platform mobile framework |
| **Expo** | Development & deployment |
| **TypeScript** | Type-safe JavaScript |
| **Redux Toolkit** | State management |
| **React Navigation** | Tab-based routing |
| **SQLite** | Local data storage |
| **Tesseract.js** | OCR text extraction |
| **React Native Paper** | UI components |
| **Axios** | API calls |

## Financial Metrics Tracked

### Income Metrics
- Gross Revenue
- Net Revenue (after fees)
- Revenue by Platform
- Sales by Category

### Expense Metrics
- Cost of Goods Sold (COGS)
- Packaging & Shipping Costs
- Platform Fees (Depop: 10%, Vinted: 5%, eBay: 12.5%)
- Operational Expenses

### Profit Metrics
- Gross Profit & Margin
- Operating Profit & Margin
- Net Profit & Margin
- Profit per Unit

### Performance Metrics
- Return on Investment (ROI)
- Average Selling Price
- Average Cost per Unit
- Conversion Rate
- Units Sold

### Tax & Accounting
- Taxable Income
- Estimated Tax Liability (20% default)

## Installation & Setup

### Prerequisites
- Node.js 16+ and npm/yarn
- Expo CLI: `npm install -g expo-cli`
- iOS Simulator (Mac) or Android Emulator

### Step 1: Install Dependencies
```bash
cd depop-sales-manager
npm install
```

### Step 2: Configure Environment
```bash
cp .env.example .env
```

Edit `.env` and add your API keys:
```
EXPO_PUBLIC_DEPOP_API_KEY=your_key
EXPO_PUBLIC_VINTED_API_KEY=your_key
EXPO_PUBLIC_EBAY_API_KEY=your_key
```

### Step 3: Start Development Server
```bash
expo start
```

### Step 4: Run on Device/Emulator
- **iOS**: Press `i`
- **Android**: Press `a`
- **Web**: Press `w`

## Platform API Setup

### Depop
1. Register as developer on [Depop Developer Portal](https://developer.depop.com)
2. Create an application
3. Get API key and add to `.env`

### Vinted
1. Visit [Vinted API Documentation](https://www.vinted.com/api)
2. Request API access
3. Add credentials to `.env`

### eBay
1. Register on [eBay Developer Platform](https://developer.ebay.com)
2. Create application
3. Generate OAuth tokens
4. Add to `.env`

## Usage Guide

### Adding Sales Data

**Manual Entry:**
1. Go to Revenue Tracker tab
2. Click "+ Add Sale"
3. Fill in item details
4. Data automatically calculates profit

**Via Screenshot:**
1. Go to Screenshot Extractor (in Dashboard)
2. Tap "Take Screenshot" or upload image
3. OCR extracts price, date, item name
4. Review and confirm extracted data
5. Data syncs to master spreadsheet

### Uploading to Multiple Platforms

1. Go to Bulk Upload tab
2. Enter item details:
   - Title & description
   - Price & shipping
   - Item condition
   - Upload images (multiple)
3. Select platforms: Depop, Vinted, eBay
4. Click "Add to Queue"
5. Click "Upload All" to upload simultaneously

### Financial Analysis

**Dashboard:**
- View key metrics at a glance
- Track profit trends
- Monitor platform performance

**Revenue Tracker:**
- See detailed spreadsheet of all sales
- Filter by date range, platform, category
- Export financial reports

**Calculator:**
- Calculate profit margins
- Determine break-even prices
- Estimate tax liabilities
- Calculate ROI

## Database Schema

### revenue_entries Table
```sql
CREATE TABLE revenue_entries (
  id TEXT PRIMARY KEY,
  date TEXT NOT NULL,
  itemName TEXT NOT NULL,
  purchasePrice REAL NOT NULL,
  sellingPrice REAL NOT NULL,
  platform TEXT NOT NULL,
  profit REAL NOT NULL,
  category TEXT,
  notes TEXT,
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

### bulk_uploads Table
```sql
CREATE TABLE bulk_uploads (
  id TEXT PRIMARY KEY,
  itemName TEXT NOT NULL,
  description TEXT,
  price REAL NOT NULL,
  shippingCost REAL,
  condition TEXT,
  category TEXT,
  images TEXT,
  platforms TEXT,
  uploadStatus TEXT,
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

## API Integration Examples

### Extract OCR Data
```typescript
import OCRService from './services/OCRService';

const data = await OCRService.extractText(imagePath);
console.log(data.data.price); // Extracted price
```

### Add Revenue Entry
```typescript
import DatabaseService from './services/DatabaseService';

await DatabaseService.addRevenueEntry({
  id: 'unique-id',
  date: '2024-01-15',
  itemName: 'Vintage Jacket',
  purchasePrice: 20,
  sellingPrice: 45,
  platform: 'depop',
  profit: 25,
  category: 'clothing',
});
```

### Calculate Metrics
```typescript
import FinanceService from './services/FinanceService';

const metrics = FinanceService.calculateMetrics(entries);
console.log(metrics.profitMargin); // Percentage
console.log(metrics.totalProfit); // Currency amount
```

### Upload to Multiple Platforms
```typescript
import ImageUploadService from './services/ImageUploadService';

const results = await ImageUploadService.uploadToMultiplePlatforms({
  itemName: 'Shirt',
  description: 'Vintage band tee',
  price: 25,
  shippingCost: 2.99,
  images: ['file:///path/to/image.jpg'],
  platforms: { depop: true, vinted: true, ebay: false }
});
```

## Financial Formulas

### Profit Calculation
```
Profit = Selling Price - Purchase Price
```

### Profit Margin
```
Profit Margin (%) = (Profit / Selling Price) × 100
```

### Net Revenue (After Platform Fees)
```
Net Revenue = Selling Price - (Selling Price × Platform Fee Rate)
```

### Platform Fees by Platform
- **Depop**: 10% of selling price
- **Vinted**: 5% of selling price
- **eBay**: 12.5% of selling price
- **Poshmark**: 20% of selling price
- **Mercari**: 10% of selling price
- **Facebook**: 5% of selling price

### Net Profit (After All Expenses)
```
Net Profit = Selling Price - Purchase Price - Shipping Cost - Platform Fees - Other Expenses
```

### Break-Even Price
```
Break-Even = Cost / (1 - Desired Margin)
Example: Cost £20, 30% margin: £20 / 0.7 = £28.57
```

### Return on Investment (ROI)
```
ROI (%) = (Profit / Total Investment) × 100
```

### Estimated Tax Liability
```
Tax = Net Profit × Tax Rate
Default: 20% of net profit (adjust to your jurisdiction)
```

## Best Practices

### Data Entry
- Always verify OCR-extracted prices
- Update items daily for accurate profit tracking
- Use consistent category names
- Add notes for unusual transactions

### Financial Management
- Export reports monthly
- Monitor profit margins for unprofitable items
- Track costs to identify profit optimization opportunities
- Review platform fee impacts quarterly

### Image Upload
- Use high-quality product photos
- Write accurate descriptions
- Include all specifications
- Verify uploads succeeded before deleting originals

### Security
- Store `.env` securely
- Don't commit API keys to git
- Use strong device passwords
- Regular data backups recommended

## Troubleshooting

### OCR Not Working
- Ensure image is clear and well-lit
- Try different image formats (JPG works best)
- Check image has sufficient resolution (min 800px width)

### Upload Failures
- Verify API credentials in `.env`
- Check internet connection
- Ensure item details are complete
- Review platform-specific requirements

### Database Errors
- Clear app cache: Settings > Storage > Clear Cache
- Reinstall app if corruption suspected
- Backup data via export before major updates

### Performance Issues
- Reduce number of entries shown (use pagination)
- Close other apps running in background
- Update to latest app version
- Restart device if needed

## Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Roadmap

- [x] Core spreadsheet functionality
- [x] OCR screenshot extraction
- [x] Multi-platform upload
- [x] Financial calculations
- [ ] Sourcing tab (inventory management)
- [ ] Cloud backup & sync
- [ ] Advanced analytics dashboard
- [ ] Multi-user support
- [ ] API webhooks
- [ ] AI-powered pricing suggestions
- [ ] Automated tax reports
- [ ] Payment processing integration

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For issues, feature requests, or questions:
- Open an issue on GitHub
- Check existing issues for solutions
- Review troubleshooting guide above

## Acknowledgments

- Tesseract.js for OCR capabilities
- React Native community
- Expo for simplified development
- All platform partners (Depop, Vinted, eBay)

---

**Version**: 1.0.0  
**Last Updated**: April 2026  
**Status**: Active Development
