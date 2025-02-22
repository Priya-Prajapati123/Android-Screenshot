# Android-Screenshot
package com.example.screenshot

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.text.font.FontWeight.Companion.Bold
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.res.stringResource
import androidx.compose.ui.text.style.TextAlign
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import com.example.screenshot.ui.theme.ScreenshotTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            ScreenshotTheme {
                Surface(modifier = Modifier.fillMaxSize()) {
                    Greeting(
                        name = "All tasks completed",
                        message = "Nice work!",
                    )
                }
            }
        }
    }
}

@Composable
fun Greeting(name: String,message:String,modifier: Modifier = Modifier) {
    val image = painterResource(R.drawable.ic_task_completed)
    Column(
        verticalArrangement = Arrangement.Center,
        horizontalAlignment = Alignment.CenterHorizontally,
        modifier = Modifier.padding(24.dp))
         {
        Image(
            painter = image,
            contentDescription = null
        )
        Text (
            text = name,
            fontWeight = Bold,
            modifier = modifier.padding(top = 24.dp,bottom = 8.dp)
        )

        Text(
            text = message,
            fontSize = 16.sp,
        )
    }
}

@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    ScreenshotTheme {
        Greeting(name = stringResource(R.string.name),message = stringResource(R.string.message))
    }
}
