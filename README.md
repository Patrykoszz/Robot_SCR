HAL_GPIO_WritePin(IN1_L_GPIO_Port, IN1_L_Pin, GPIO_PIN_SET);
	  HAL_GPIO_WritePin(IN2_L_GPIO_Port, IN2_L_Pin, GPIO_PIN_RESET);

	  HAL_GPIO_WritePin(IN3_L_GPIO_Port, IN3_L_Pin, GPIO_PIN_SET);
	  HAL_GPIO_WritePin(IN4_L_GPIO_Port, IN4_L_Pin, GPIO_PIN_RESET);

	      // Ustawienie mocy silników na 60% (600 z 1000)
	  __HAL_TIM_SET_COMPARE(&htim1, TIM_CHANNEL_1, 400); // Lewy
	  HAL_Delay(2000);
	  __HAL_TIM_SET_COMPARE(&htim1, TIM_CHANNEL_1, 0);
	  __HAL_TIM_SET_COMPARE(&htim1, TIM_CHANNEL_2, 400);// Prawy

	  HAL_Delay(5000); // Czekaj 3 sekundy


	      // --- FAZA 2: ZATRZYMANIE (2 sekundy) ---

	      // Hamulec - zmiana mocy na 0

	  __HAL_TIM_SET_COMPARE(&htim1, TIM_CHANNEL_2, 0);

	  HAL_Delay(2000);
