QTreeWidget* treewidget = new QTreeWidget;
    treewidget->setHeaderHidden(true);  
    treewidget->expandAll();
    _terrainItem = new QTreeWidgetItem(treewidget); 
    _terrainItem->setText(0,""); 
    treewidget->addTopLevelItem(_terrainItem);
    _imageItem = new QTreeWidgetItem(treewidget);
    _imageItem->setText(0,""); 
    treewidget->addTopLevelItem(_imageItem);
    _threedTilesItem = new QTreeWidgetItem(treewidget); 
    _threedTilesItem->setText(0,""); 
    treewidget->addTopLevelItem(_threedTilesItem);
connect(treewidget,SIGNAL(itemClicked(QTreeWidgetItem*,int)),this,SLOT(onItemClick(QTreeWidgetItem*,int))); 


QTreeWidgetItem *item = new QTreeWidgetItem(_threedTilesItem);
item->setCheckState(0,Qt::Checked); //开启复选框
void LayerModuleDialog::onItemClick(QTreeWidgetItem *item, int column)
{
    QTreeWidgetItem *parent = item->parent();  //获取父节点 
     if(NULL==parent) //注意：最顶端项是没有父节点的 
         return;
    if(parent->text(0) == "图层")
    {
        if(item->checkState(0) == Qt::Unchecked)
        {
        }else if(item->checkState(0) == Qt::Checked)        
        {
        }    
    }
}


