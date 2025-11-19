<!-- Renomme ce fichier en MainActivity.java dans ton projet -->
<code>
package com.skimmy.browser;

import android.os.Bundle;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.widget.EditText;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;
import androidx.swiperefreshlayout.widget.SwipeRefreshLayout;

public class MainActivity extends AppCompatActivity {

    private WebView webView;
    private EditText urlBar;
    private String defaultEngine = "https://skimmy.wuaze.com";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.index2);

        SwipeRefreshLayout swipe = findViewById(R.id.swipe);
        webView = findViewById(R.id.webView);
        urlBar = findViewById(R.id.urlBar);
        Button btnGo = findViewById(R.id.btnGo);

        webView.setWebViewClient(new WebViewClient());
        webView.getSettings().setJavaScriptEnabled(true);
        webView.loadUrl(defaultEngine);

        btnGo.setOnClickListener(v -> {
            String url = urlBar.getText().toString();
            if (!url.startsWith("http")) {
                url = "https://" + url;
            }
            webView.loadUrl(url);
        });

        swipe.setOnRefreshListener(() -> {
            webView.reload();
            swipe.setRefreshing(false);
        });
    }

    @Override
    public void onBackPressed() {
        if (webView.canGoBack()) webView.goBack();
        else super.onBackPressed();
    }
}
</code>
