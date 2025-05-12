# ⚙️ Smart Nutrition Estimator - Backend API

Backend for the Smart Nutrition Estimator by Pankaj Paliwal (VYB AI challenge).

## 🔥 Hosted at
- **[Smart Nutrition Estimator - Backend](https://back-smart-production.up.railway.app/)**

## 📋 Endpoints

### `GET /`
Health check for the API.

### `POST /analyze-dish`
Takes a dish name and returns per-serving nutrition data.

**Request:**
```json
{
  "dish_name": "Paneer Butter Masala"
}
```

**Response:**
```json
{
  "dish": "Paneer Butter Masala",
  "ingredients_extracted": ["paneer", "butter", "tomato"],
  "logs": ["⚠️ butter not matched"],
  "category": "Veg Gravy",
  "serving_weight_g": 180,
  "nutrition_per_serving": {
    "calories": 250,
    "protein": 12,
    "fat": 18
  }
}
```

### `POST /analyze-json`
Batch analysis of multiple dishes with optional known issues.

## 🛠️ How It Works
1. **Ingredient Extraction**: Using Gemini 1.5 Flash
2. **Fuzzy Matching**: Matching ingredients to nutrition database
3. **Nutrition Calculation**: Per-serving values based on matched ingredients
4. **Dish Classification**: Categorizing dishes (Veg Gravy, Veg Dry, etc.)

## ⚙️ Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/smart-nutrition-estimator.git
   cd smart-nutrition-estimator
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the server**:
   ```bash
   uvicorn app:app --reload
   ```

4. **Visit API docs** at `http://127.0.0.1:8000/docs`

**Built by Pankaj Paliwal for the VYB AI challenge.**
